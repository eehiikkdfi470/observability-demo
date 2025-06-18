Rendering the Argo CD Helm Chart
    "kubectl kustomize --enable-helm --load-restrictor LoadRestrictionsNone > _rendered_argocd.yaml"

Purpose: This command renders the Argo CD Helm chart into a Kubernetes manifest file (_rendered_argocd.yaml).

Key Flags:
--enable-helm: Enables Helm chart rendering within a Kustomize configuration.
--load-restrictor LoadRestrictionsNone: Disables restrictions on loading local files, which is useful when working with local Helm charts or Kustomize overlays.
Output: The rendered YAML file (_rendered_argocd.yaml) contains all the Kubernetes resources (Deployments, Services, ConfigMaps, etc.) required to install Argo CD.

Installation of Argocd 
    "kubectl apply -f _rendered_argocd.yaml"

Upgrade Argo CD:
While upgrading ArgoCD , replace the version of ArgoCD application at /apps/argocd/overlays/{env}/kustomization.yaml with latest version .

Once kustomization.yaml file is updated with latest version - run the rendered command and kubectl apply -f command as metnioend above.
