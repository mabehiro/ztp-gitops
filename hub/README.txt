Add CA certificate
https://docs.openshift.com/container-platform/4.7/cicd/builds/setting-up-trusted-ca.html#configmap-adding-ca_setting-up-trusted-ca

create configmap registry-cas -n openshift-config --from-file=quay.john.com..8443=/home/user/ca.crt
patch image.config.openshift.io/cluster --patch '{"spec":{"additionalTrustedCA":{"name":"registry-cas"}}}' --type=merge
