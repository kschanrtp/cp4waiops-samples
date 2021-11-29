# IBM Cloud Pak for Watson AIOps AI Manager prerequisite checker tool

The prerequisite checker tool can be used to validate whether a Red Hat OpenShift Container Platform cluster has the required resources available to enable a successful installation of IBM Cloud Pak for Watson AIOps AI Manager. This tool completes the following checks and generates an installation readiness report:

- **OpenShift version check** : Checks whether the Red Hat OpenShift Container Platform cluster version is a fully supported Extended Update Support (EUS) version and compatible for installing IBM Cloud Pak for Watson AIOps AI Manager. OpenShift Container Platform 4.6 and 4.8 are currently under full support and compatible. OpenShift Container Platform 4.7 full support is ended by Red Hat and is not supported for installing IBM Cloud Pak for Watson AIOps AI Manager.

- **Storage check**: Checks whether a storage class that uses a supported storage provider (Portworx or Red Hat Openshift Data Foundation (ODF)) is available on the cluster. For more information, see the IBM Documentation [Storage considerations](https://ibm.biz/storage_consideration_320).

- **Network policy check**: Checks whether the network policy is configured for the AI Manager routes, which allow external traffic to reach the routes. For more information about how the network policy is configured, see the IBM Documentation [Configure network policies](https://ibm.biz/aiops_netpolicy_320).

-  **OpenShift registry setup check**: Checks whether the Red Hat OpenShift Image Registry is configured. For more information about how to set up the registry, see the Red Hat documentation [Configuring the registry for vSphere](https://docs.openshift.com/container-platform/4.8/registry/configuring_registry_storage/configuring-registry-storage-vsphere.html).

- **Small or large profile install check**: Checks whether the cluster has enough resources (vCPU, Memory, and Nodes) for installing a small or large profile of IBM Cloud Pak for Watson AIOps AI Manager. For more information, see the IBM Documentation [Hardware requirements](https://ibm.biz/aiops_hardware_320).

- **Entitlement Secret check**: Checks whether a secret called ibm-entitlement-key or a global pull secret called pull-secret (global pull secret found in openshift-config namespace) have been created. For more information, see the IBM Documentation [Entitlement Keys](https://ibm.biz/entitlement_keys_320)

## Getting started

Clone the following GitHub repository:

```
  git clone https://github.com:IBM/cp4waiops-samples.git 
  cd prereq-checker/3.2
```

## Running the prerequisite checker tool script

NOTE: Before you run the script make sure that you are in the namespace where you are planning to install IBM Cloud Pak for Watson AIOps AI Manager.
```
oc project <namespace_name>
ex: oc project cp4waiops
```

To run the prerequisite checker tool, run the following command:
```
  ./prereq.sh
```