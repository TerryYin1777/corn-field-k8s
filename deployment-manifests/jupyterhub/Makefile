export VERSION=3.0.3
export RELEASE_NAME=jupyterhub
export NAMESPACE=jupyterhub
export CHART_URL=https://hub.jupyter.org/helm-chart/
export CHART=jupyterhub

repo:
	helm repo add ${CHART} ${CHART_URL}
	helm repo update

# should deploy in the namespace where the service account can access dns server
# or assume a service account that has same permission
template:
	helm template \
	--namespace ${NAMESPACE} \
	--repo ${CHART_URL} \
	--version ${VERSION} \
	--release-name ${RELEASE_NAME} \
	--values ./values.yaml > ./kustomization/deployment.yaml