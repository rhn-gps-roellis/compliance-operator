# compliance-operator

## Official documentation can be found here: 
https://docs.openshift.com/container-platform/4.8/security/compliance_operator/compliance-operator-understanding.html

https://docs.openshift.com/container-platform/4.8/security/compliance_operator/compliance-operator-installation.html

https://docs.openshift.com/container-platform/4.8/security/compliance_operator/compliance-operator-supported-profiles.html


## Install compliance operator:

1. `oc get packagemanifests -n openshift-marketplace | grep compliance`, verify that your olm sources provide the compliance operator.  Example output from successful command:
compliance-operator                                  Red Hat Operators     6d20h

2. `oc describe packagemanifests compliance-operator -n openshift-marketplace`, verify install modes and versions available.  You will need this when you want to create your operator subscription. See manifest.md (in main dir of this repo) for an example of the output from this command.  

3.  From the manifest, we can see the following install modes, and the available channel is release-0.1.  AllNamespaces is not supported.  As such, create manifest for a namespace for this operator to use and an operator group. (see compliance_operator.yaml).  Also create a manifest for this operator's subscription.

`      Install Modes:
        Supported:  true
        Type:       OwnNamespace
        Supported:  true
        Type:       SingleNamespace
        Supported:  true
        Type:       MultiNamespace
        Supported:  false
        Type:       AllNamespaces`

## Configure Scan Setting and Scan Setting Binding