# Workflow

There are many workflows that customers can design.

1. have a root gitrepo bootstrapper project that has the manifests that adds a gitrepo channel with the subscription target as local-cluster
2. this repo should be organized by the namespaces that the mcm application projects will deploy.

bootstrap-gitrepo-root
  /bootstrap-gitrepo
    channel.yaml
    subscription.yaml to local-cluster

gitrepo-root
  /bookinfo
  /bookinfo-project
  /bookinfo-entitlemen
  /mcm-policy
