Rendering the Argo CD Helm Chart
    "kubectl kustomize --enable-helm --load-restrictor LoadRestrictionsNone > _rendered_argocd.yaml"

Purpose: This command renders the Argo CD Helm chart into a Kubernetes manifest file (_rendered_argocd.yaml).

Key Flags:
--enable-helm: Enables Helm chart rendering within a Kustomize configuration.
--load-restrictor LoadRestrictionsNone: Disables restrictions on loading local files, which is useful when working with local Helm charts or Kustomize overlays.
Output: The rendered YAML file (_rendered_argocd.yaml) contains all the Kubernetes resources (Deployments, Services, ConfigMaps, etc.) required to install Argo CD.

Installation of Argocd 
    "kubectl apply -f _rendered_argocd.yaml"

