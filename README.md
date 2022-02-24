# compliance-operator

## Official documentation can be found here: 
https://docs.openshift.com/container-platform/4.8/security/compliance_operator/compliance-operator-understanding.html

https://docs.openshift.com/container-platform/4.8/security/compliance_operator/compliance-operator-installation.html

https://docs.openshift.com/container-platform/4.8/security/compliance_operator/compliance-operator-supported-profiles.html


## Install compliance operator:

1. `oc get packagemanifests -n openshift-marketplace | grep compliance`, verify that your olm sources provide the compliance operator.  Example output from successful command:
compliance-operator                                  Red Hat Operators     6d20h

2. `oc describe packagemanifests compliance-operator -n openshift-marketplace`, verify install modes and versions available.  You will need this when you want to create your operator subscription. See manifest.yaml (in main dir of this repo) for an example of the output from this command.  

3.  From the manifest, we can see the following install modes, and the available channel is release-0.1.  AllNamespaces is not supported.  As such, create manifest for a namespace for this operator to use and an operator group. (see CO_install.yaml).create a manifest for this operator's subscription in the same yaml manifest.

`      Install Modes:
        Supported:  true
        Type:       OwnNamespace
        Supported:  true
        Type:       SingleNamespace
        Supported:  true
        Type:       MultiNamespace
        Supported:  false
        Type:       AllNamespaces`

4.  `oc apply -f CO_install.yaml` to install the operator from CLI.  Else, this can be imported and added to a gitops pipeline.

## Configure Scan Setting, Scan Setting Binding, and results server

5.  After install complete and confirmed, it's time to configure scan settings.  This is done by creating a yaml manifest declaring the settings (seen in this repo as CO__ss_ssb.yaml). The scan settings tell the cluster how often to scan, which type of nodes to scan, and define any required tolerations to allow the scans to run on any tainted nodes.  Additionally, auto update/auto apply are controlled by the contents of this manifest.  When using default-auto-apply, False requires manual intervention for remediation, true will perform such actions automatically IN THEORY.  In practice, there will still be several items which will require manual intervention.  As the default and default-auto-apply scansettings automatically exist in the base install of the compliance operator, run the following command to update any edits to these policies from the CLI.  Else, this can be included into any gitops workflow.
`oc replace -f CO_ss.yaml`

6.  With this complete, its time to configure scan setting bindings.  This is done by creating a yaml manifest declaring the settings (seen in this repo as CO_ssb.yaml) As a reminder, several individual manifests can be combined into one singular manifest file.  This manifest declares which compliance profile the cluster will be scanned against / will be made compliant to.  For reference, all of the supported profiles are found in the reference link above.  For this implementation example, ocp4-cis and ocp4-cis-node are used.

7. `oc create -f CO_ssb.yaml` using CLI to create the Scan Settings binding.  This can also be added to a gitops pipeline/workflow for automation.

8.  Finally, if the environment does not permit deployment of PVs/PVCs onto master nodes, a resultserver pod can be configured.  An example of such is located in CO_rs.yaml.

9. `oc create -f CO_rs.yaml` using CLI to create the reportserver pods.  This can also be added to a gitops pipeline/workflow for automation.

