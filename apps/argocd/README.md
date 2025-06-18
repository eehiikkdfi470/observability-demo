**Rendering the Argo CD Helm Chart**

kubectl kustomize --enable-helm --load-restrictor LoadRestrictionsNone > _rendered_argocd.yaml
Purpose:
This command renders the Argo CD Helm chart into a Kubernetes manifest file named _rendered_argocd.yaml.

**Key Flags:**

--enable-helm: Enables Helm chart rendering within a Kustomize configuration.
--load-restrictor LoadRestrictionsNone: Disables restrictions on loading local files, useful when working with local Helm charts or Kustomize overlays.

Output:

The rendered YAML file (_rendered_argocd.yaml) contains all the Kubernetes resources (Deployments, Services, ConfigMaps, etc.) required to install Argo CD.

**Installation of Argo CD**

kubectl apply -f _rendered_argocd.yaml
This command applies the rendered manifest to your Kubernetes cluster, installing Argo CD.

**Upgrade Argo CD**

When upgrading Argo CD:

Update the version of the Argo CD application in the file:

/apps/argocd/overlays/{env}/kustomization.yaml

Replace {env} with your environment name and set the version to the latest Argo CD release.
After updating the kustomization.yaml file, rerun the render command and apply command as described above:

**kubectl kustomize --enable-helm --load-restrictor LoadRestrictionsNone > _rendered_argocd.yaml**

**kubectl apply -f _rendered_argocd.yaml**

This will upgrade Argo CD to the new version on your cluster.
