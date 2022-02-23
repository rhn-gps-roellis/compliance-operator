Name:         compliance-operator
Namespace:    openshift-marketplace
Labels:       catalog=redhat-operators
              catalog-namespace=openshift-marketplace
              operatorframework.io/arch.amd64=supported
              operatorframework.io/os.linux=supported
              provider=Red Hat Inc.
              provider-url=www.redhat.com
Annotations:  <none>
API Version:  packages.operators.coreos.com/v1
Kind:         PackageManifest
Metadata:
  Creation Timestamp:  2022-02-16T19:53:02Z
Spec:
Status:
  Catalog Source:               redhat-operators
  Catalog Source Display Name:  Red Hat Operators
  Catalog Source Namespace:     openshift-marketplace
  Catalog Source Publisher:     Red Hat
  Channels:
    Current CSV:  compliance-operator.v0.1.32
    Current CSV Desc:
      Annotations:
        Alm - Examples:  [
  {
    "apiVersion": "compliance.openshift.io/v1alpha1",
    "kind": "ComplianceScan",
    "metadata": {
      "name": "example-compliancescan"
    },
    "spec": {
      "content": "ssg-rhcos4-ds.xml",
      "profile": "xccdf_org.ssgproject.content_profile_moderate"
    }
  },
  {
    "apiVersion": "compliance.openshift.io/v1alpha1",
    "kind": "ComplianceScan",
    "metadata": {
      "name": "example-compliancescan"
    },
    "spec": {
      "content": "ssg-ocp4-ds.xml",
      "profile": "xccdf_org.ssgproject.content_profile_moderate",
      "scanType": "Platform"
    }
  },
  {
    "apiVersion": "compliance.openshift.io/v1alpha1",
    "kind": "ComplianceSuite",
    "metadata": {
      "name": "example-compliancesuite"
    },
    "spec": {
      "autoApplyRemediations": false,
      "scans": [
        {
          "content": "ssg-rhcos4-ds.xml",
          "contentImage": "registry.redhat.io/openshift4/compliance-content-rhel8@sha256:4529b9bb32c1846a38e38363fa872713b1c1e6b26b34d887813432f97cff368c",
          "name": "workers-scan",
          "nodeSelector": {
            "node-role.kubernetes.io/worker": ""
          },
          "profile": "xccdf_org.ssgproject.content_profile_moderate"
        },
        {
          "content": "ssg-ocp4-ds.xml",
          "contentImage": "registry.redhat.io/openshift4/compliance-content-rhel8@sha256:4529b9bb32c1846a38e38363fa872713b1c1e6b26b34d887813432f97cff368c",
          "name": "platform-scan",
          "profile": "xccdf_org.ssgproject.content_profile_moderate",
          "scanType": "Platform"
        }
      ],
      "schedule": "0 1 * * *"
    }
  },
  {
    "apiVersion": "compliance.openshift.io/v1alpha1",
    "kind": "ProfileBundle",
    "metadata": {
      "name": "ocp4"
    },
    "spec": {
      "contentFile": "ssg-ocp4-ds.xml",
      "contentImage": "registry.redhat.io/openshift4/compliance-content-rhel8@sha256:4529b9bb32c1846a38e38363fa872713b1c1e6b26b34d887813432f97cff368c"
    }
  },
  {
    "apiVersion": "compliance.openshift.io/v1alpha1",
    "autoApplyRemediations": false,
    "debug": true,
    "kind": "ScanSetting",
    "metadata": {
      "name": "my-companys-constraints"
    },
    "rawResultStorage": {
      "rotation": 10,
      "size": "2Gi"
    },
    "roles": [
      "worker",
      "master"
    ],
    "schedule": "0 1 * * *"
  },
  {
    "apiVersion": "compliance.openshift.io/v1alpha1",
    "kind": "ScanSettingBinding",
    "metadata": {
      "name": "nist-moderate"
    },
    "profiles": [
      {
        "apiGroup": "compliance.openshift.io/v1alpha1",
        "kind": "Profile",
        "name": "rhcos4-moderate"
      }
    ],
    "settingsRef": {
      "apiGroup": "compliance.openshift.io/v1alpha1",
      "kind": "ScanSetting",
      "name": "default"
    }
  },
  {
    "apiVersion": "compliance.openshift.io/v1alpha1",
    "kind": "TailoredProfile",
    "metadata": {
      "name": "example-tailoredprofile"
    },
    "spec": {
      "disableRules": [
        {
          "name": "ocp4-file-permissions-node-config",
          "rationale": "This breaks X application."
        },
        {
          "name": "ocp4-account-disable-post-pw-expiration",
          "rationale": "testing this"
        },
        {
          "name": "ocp4-accounts-no-uid-except-zero",
          "rationale": "testing this"
        },
        {
          "name": "ocp4-audit-rules-dac-modification-chmod",
          "rationale": "testing this"
        },
        {
          "name": "ocp4-audit-rules-dac-modification-chown",
          "rationale": "testing this"
        },
        {
          "name": "ocp4-audit-rules-dac-modification-fchmod",
          "rationale": "testing this"
        },
        {
          "name": "ocp4-audit-rules-dac-modification-fchmodat",
          "rationale": "testing this"
        },
        {
          "name": "ocp4-audit-rules-dac-modification-fchown",
          "rationale": "testing this"
        }
      ],
      "extends": "ocp4-moderate",
      "setValues": [
        {
          "name": "ocp4-var-selinux-state",
          "rationale": "trolling dwalsh",
          "value": "permissive"
        }
      ],
      "title": "My little profile"
    }
  }
]
        Capabilities:                                    Seamless Upgrades
        Categories:                                      Monitoring,Security
        olm.skipRange:                                   >=0.1.17 <0.1.32
        operatorframework.io/cluster-monitoring:         true
        operatorframework.io/suggested-namespace:        openshift-compliance
        operators.openshift.io/infrastructure-features:  ["disconnected", "fips"]
        Repository:                                      https://github.com/openshift/compliance-operator
        Support:                                         Red Hat Inc.
      Apiservicedefinitions:
      Customresourcedefinitions:
        Owned:
          Description:  ComplianceCheckResult represent a result of a single compliance "test"
          Kind:         ComplianceCheckResult
          Name:         compliancecheckresults.compliance.openshift.io
          Version:      v1alpha1
          Description:  ComplianceRemediation represents a remediation that can be applied to the cluster to fix the found issues.
          Kind:         ComplianceRemediation
          Name:         complianceremediations.compliance.openshift.io
          Version:      v1alpha1
          Description:  ComplianceScan represents a scan with a certain configuration that will be applied to objects of a certain entity in the host. These could be nodes that apply to a certain nodeSelector, or the cluster itself.
          Kind:         ComplianceScan
          Name:         compliancescans.compliance.openshift.io
          Version:      v1alpha1
          Description:  ComplianceSuite represents a set of scans that will be applied to the cluster. These should help deployers achieve a certain compliance target.
          Kind:         ComplianceSuite
          Name:         compliancesuites.compliance.openshift.io
          Version:      v1alpha1
          Description:  ProfileBundle is the Schema for the profilebundles API
          Kind:         ProfileBundle
          Name:         profilebundles.compliance.openshift.io
          Version:      v1alpha1
          Description:  Profile is the Schema for the profiles API
          Kind:         Profile
          Name:         profiles.compliance.openshift.io
          Version:      v1alpha1
          Description:  Rule is the Schema for the rules API
          Kind:         Rule
          Name:         rules.compliance.openshift.io
          Version:      v1alpha1
          Description:  ScanSettingBinding is the Schema for the scansettingbindings API
          Kind:         ScanSettingBinding
          Name:         scansettingbindings.compliance.openshift.io
          Version:      v1alpha1
          Description:  ScanSetting is the Schema for the scansettings API
          Kind:         ScanSetting
          Name:         scansettings.compliance.openshift.io
          Version:      v1alpha1
          Description:  TailoredProfile is the Schema for the tailoredprofiles API
          Kind:         TailoredProfile
          Name:         tailoredprofiles.compliance.openshift.io
          Version:      v1alpha1
          Description:  Variable describes a tunable in the XCCDF profile
          Kind:         Variable
          Name:         variables.compliance.openshift.io
          Version:      v1alpha1
      Description:      An operator which runs OpenSCAP and allows you to keep your cluster compliant with the security benchmark you need.
      Display Name:     Compliance Operator
      Install Modes:
        Supported:  true
        Type:       OwnNamespace
        Supported:  true
        Type:       SingleNamespace
        Supported:  true
        Type:       MultiNamespace
        Supported:  false
        Type:       AllNamespaces
      Keywords:
        security
        compliance
        openscap
        audit
      Links:
        Name:  Compliance Operator upstream repo
        URL:   https://github.com/openshift/compliance-operator
        Name:  Compliance Operator documentation
        URL:   https://docs.openshift.com/container-platform/4.7/security/compliance_operator/compliance-operator-understanding.html
      Maintainers:
        Email:   support@redhat.com
        Name:    Red Hat Support
      Maturity:  alpha
      Provider:
        Name:  Red Hat Inc.
        URL:   www.redhat.com
      Related Images:
        registry.redhat.io/openshift4/compliance-openscap-rhel8@sha256:867c6d4205653d8a954d234cbaf470313009eb983d4f455fb45f49c4a7764422
        registry.redhat.io/openshift4/compliance-rhel8-operator@sha256:ed68a0574ddeaf7d676403cd843f28cb586894f35dbb3ca5e06a5264bd42f030
        registry.redhat.io/openshift4/compliance-content-rhel8@sha256:4529b9bb32c1846a38e38363fa872713b1c1e6b26b34d887813432f97cff368c
      Version:    0.1.32
    Name:         4.7
    Current CSV:  compliance-operator.v0.1.48
    Current CSV Desc:
      Annotations:
        Alm - Examples:  [
  {
    "apiVersion": "compliance.openshift.io/v1alpha1",
    "kind": "ComplianceScan",
    "metadata": {
      "name": "example-compliancescan"
    },
    "spec": {
      "content": "ssg-rhcos4-ds.xml",
      "profile": "xccdf_org.ssgproject.content_profile_moderate"
    }
  },
  {
    "apiVersion": "compliance.openshift.io/v1alpha1",
    "kind": "ComplianceScan",
    "metadata": {
      "name": "example-compliancescan"
    },
    "spec": {
      "content": "ssg-ocp4-ds.xml",
      "profile": "xccdf_org.ssgproject.content_profile_moderate",
      "scanType": "Platform"
    }
  },
  {
    "apiVersion": "compliance.openshift.io/v1alpha1",
    "kind": "ComplianceSuite",
    "metadata": {
      "name": "example-compliancesuite"
    },
    "spec": {
      "autoApplyRemediations": false,
      "scans": [
        {
          "content": "ssg-rhcos4-ds.xml",
          "contentImage": "registry.redhat.io/compliance/openshift-compliance-content-rhel8@sha256:6f24fec15e651a0db1d02b5dcc2884e32e8639bda7f90f72abd8853ccdf4b166",
          "name": "workers-scan",
          "nodeSelector": {
            "node-role.kubernetes.io/worker": ""
          },
          "profile": "xccdf_org.ssgproject.content_profile_moderate"
        },
        {
          "content": "ssg-ocp4-ds.xml",
          "contentImage": "registry.redhat.io/compliance/openshift-compliance-content-rhel8@sha256:6f24fec15e651a0db1d02b5dcc2884e32e8639bda7f90f72abd8853ccdf4b166",
          "name": "platform-scan",
          "profile": "xccdf_org.ssgproject.content_profile_moderate",
          "scanType": "Platform"
        }
      ],
      "schedule": "0 1 * * *"
    }
  },
  {
    "apiVersion": "compliance.openshift.io/v1alpha1",
    "kind": "ProfileBundle",
    "metadata": {
      "name": "ocp4"
    },
    "spec": {
      "contentFile": "ssg-ocp4-ds.xml",
      "contentImage": "registry.redhat.io/compliance/openshift-compliance-content-rhel8@sha256:6f24fec15e651a0db1d02b5dcc2884e32e8639bda7f90f72abd8853ccdf4b166"
    }
  },
  {
    "apiVersion": "compliance.openshift.io/v1alpha1",
    "autoApplyRemediations": false,
    "debug": true,
    "kind": "ScanSetting",
    "metadata": {
      "name": "my-companys-constraints"
    },
    "rawResultStorage": {
      "rotation": 10,
      "size": "2Gi"
    },
    "roles": [
      "worker",
      "master"
    ],
    "schedule": "0 1 * * *"
  },
  {
    "apiVersion": "compliance.openshift.io/v1alpha1",
    "kind": "ScanSettingBinding",
    "metadata": {
      "name": "nist-moderate"
    },
    "profiles": [
      {
        "apiGroup": "compliance.openshift.io/v1alpha1",
        "kind": "Profile",
        "name": "rhcos4-moderate"
      }
    ],
    "settingsRef": {
      "apiGroup": "compliance.openshift.io/v1alpha1",
      "kind": "ScanSetting",
      "name": "default"
    }
  },
  {
    "apiVersion": "compliance.openshift.io/v1alpha1",
    "kind": "TailoredProfile",
    "metadata": {
      "name": "example-tailoredprofile"
    },
    "spec": {
      "description": "Example of a tailoredProfile that extends OCP4 FedRAMP Moderate",
      "disableRules": [
        {
          "name": "ocp4-file-permissions-node-config",
          "rationale": "This breaks X application."
        },
        {
          "name": "ocp4-account-disable-post-pw-expiration",
          "rationale": "testing this"
        },
        {
          "name": "ocp4-accounts-no-uid-except-zero",
          "rationale": "testing this"
        },
        {
          "name": "ocp4-audit-rules-dac-modification-chmod",
          "rationale": "testing this"
        },
        {
          "name": "ocp4-audit-rules-dac-modification-chown",
          "rationale": "testing this"
        },
        {
          "name": "ocp4-audit-rules-dac-modification-fchmod",
          "rationale": "testing this"
        },
        {
          "name": "ocp4-audit-rules-dac-modification-fchmodat",
          "rationale": "testing this"
        },
        {
          "name": "ocp4-audit-rules-dac-modification-fchown",
          "rationale": "testing this"
        }
      ],
      "extends": "ocp4-moderate",
      "setValues": [
        {
          "name": "ocp4-var-selinux-state",
          "rationale": "trolling dwalsh",
          "value": "permissive"
        }
      ],
      "title": "My little profile"
    }
  }
]
        Capabilities:                                    Seamless Upgrades
        Categories:                                      Monitoring,Security
        olm.skipRange:                                   >=0.1.17 <0.1.48
        operatorframework.io/cluster-monitoring:         true
        operatorframework.io/suggested-namespace:        openshift-compliance
        operators.openshift.io/infrastructure-features:  ["disconnected", "fips", "proxy-aware"]
        Repository:                                      https://github.com/openshift/compliance-operator
        Support:                                         Red Hat Inc.
      Apiservicedefinitions:
      Customresourcedefinitions:
        Owned:
          Description:  ComplianceCheckResult represent a result of a single compliance "test"
          Kind:         ComplianceCheckResult
          Name:         compliancecheckresults.compliance.openshift.io
          Version:      v1alpha1
          Description:  ComplianceRemediation represents a remediation that can be applied to the cluster to fix the found issues.
          Kind:         ComplianceRemediation
          Name:         complianceremediations.compliance.openshift.io
          Version:      v1alpha1
          Description:  ComplianceScan represents a scan with a certain configuration that will be applied to objects of a certain entity in the host. These could be nodes that apply to a certain nodeSelector, or the cluster itself.
          Kind:         ComplianceScan
          Name:         compliancescans.compliance.openshift.io
          Version:      v1alpha1
          Description:  ComplianceSuite represents a set of scans that will be applied to the cluster. These should help deployers achieve a certain compliance target.
          Kind:         ComplianceSuite
          Name:         compliancesuites.compliance.openshift.io
          Version:      v1alpha1
          Description:  ProfileBundle is the Schema for the profilebundles API
          Kind:         ProfileBundle
          Name:         profilebundles.compliance.openshift.io
          Version:      v1alpha1
          Description:  Profile is the Schema for the profiles API
          Kind:         Profile
          Name:         profiles.compliance.openshift.io
          Version:      v1alpha1
          Description:  Rule is the Schema for the rules API
          Kind:         Rule
          Name:         rules.compliance.openshift.io
          Version:      v1alpha1
          Description:  ScanSettingBinding is the Schema for the scansettingbindings API
          Kind:         ScanSettingBinding
          Name:         scansettingbindings.compliance.openshift.io
          Version:      v1alpha1
          Description:  ScanSetting is the Schema for the scansettings API
          Kind:         ScanSetting
          Name:         scansettings.compliance.openshift.io
          Version:      v1alpha1
          Description:  TailoredProfile is the Schema for the tailoredprofiles API
          Kind:         TailoredProfile
          Name:         tailoredprofiles.compliance.openshift.io
          Version:      v1alpha1
          Description:  Variable describes a tunable in the XCCDF profile
          Kind:         Variable
          Name:         variables.compliance.openshift.io
          Version:      v1alpha1
      Description:      An operator which runs OpenSCAP and allows you to keep your cluster compliant with the security benchmark you need.
      Display Name:     Compliance Operator
      Install Modes:
        Supported:  true
        Type:       OwnNamespace
        Supported:  true
        Type:       SingleNamespace
        Supported:  true
        Type:       MultiNamespace
        Supported:  true
        Type:       AllNamespaces
      Keywords:
        security
        compliance
        openscap
        audit
      Links:
        Name:  Compliance Operator upstream repo
        URL:   https://github.com/openshift/compliance-operator
        Name:  Compliance Operator documentation
        URL:   https://docs.openshift.com/container-platform/latest/security/compliance_operator/compliance-operator-understanding.html
      Maintainers:
        Email:   support@redhat.com
        Name:    Red Hat Support
      Maturity:  alpha
      Provider:
        Name:  Red Hat Inc.
        URL:   www.redhat.com
      Related Images:
        registry.redhat.io/compliance/openshift-compliance-rhel8-operator@sha256:7bec1994e923135a1a4002d0f5f4adb5c42678cd040c05bac41471baeeb92b84
        registry.redhat.io/compliance/openshift-compliance-openscap-rhel8@sha256:04a5f5c98b514275638c1d094305ccb76e9926dfdea11d9878496e8bcdfc3210
        registry.redhat.io/compliance/openshift-compliance-content-rhel8@sha256:6f24fec15e651a0db1d02b5dcc2884e32e8639bda7f90f72abd8853ccdf4b166
      Version:      0.1.48
    Name:           release-0.1
  Default Channel:  release-0.1
  Package Name:     compliance-operator
  Provider:
    Name:  Red Hat Inc.
    URL:   www.redhat.com
Events:    <none>
