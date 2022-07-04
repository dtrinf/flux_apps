# flux_apps

## Schema

``` plain
 ┌──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┐
 │                                                                                                                                                                              │
 │ flux_apps repository                                                                                                                                                         │
 │                                                                                                                                                                              │
 ├──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┤
 │                                                                                                                                                                              │
 │   ┌────────────────────────────────────┐     ┌───────────────────────────────────┐     ┌─────────────────────────────────────┐     ┌─────────────────────────────────────┐   │
 │   │                                    │     │                                   │     │                                     │     │                                     │   │
 │   │ base                               │     │ client1                           │     │ client2                             │     │ clientN                             │   │
 │   │                                    │     │                                   │     │                                     │     │                                     │   │
 │   └─┬──────────────────────────────────┘     └─┬─────────────────────────────────┘     └─┬───────────────────────────────────┘     └─┬───────────────────────────────────┘   │
 │     │                                          │                                         │                                           │                                       │
 │     ├─► {app1}                                 ├─► dev                                   ├─► dev                                     ├─► dev                                 │
 │     │    │                                     │   │                                     │   │                                       │   │                                   │
 │     │    ├─► kustomization.yaml                │   ├─► app1                              │   ├─► app1                                │   ├─► app2                            │
 │     │    │                                     │   │   │                                 │   │   │                                   │   │   │                               │
 │     │    ├─► deployment.yaml                   │   │   └─► kustomization.yaml            │   │   └─► kustomization.yaml              │   │   └─► kustomization.yaml          │
 │     │    │                                     │   │                                     │   │                                       │   │                                   │
 │     │    └─► repository.yaml                   │   ├─► app2                              │   ├─► app3                                │   ├─► app3                            │
 │     │                                          │   │   │                                 │   │   │                                   │   │   │                               │
 │     ├─► {app2}                                 │   │   ├─► kustomization.yaml            │   │   ├─► kustomization.yaml              │   │   ├─► kustomization.yaml          │
 │     │    │                                     │   │   │                                 │   │   │                                   │   │   │                               │
 │     │    ├─► kustomization.yaml                │   │   └─► values.yaml                   │   │   └─► values.yaml                     │   │   └─► values.yaml                 │
 │     │    │                                     │   │                                     │   │                                       │   │                                   │
 │     │    ├─► deployment.yaml                   │   └─► kustomization.yaml                │   └─► kustomization.yaml                  │   └─► kustomization.yaml              │
 │     │    │                                     │                                         │                                           │                                       │
 │     │    └─► repository.yaml                   ├─► qa                                    ├─► qa                                      ├─► qa                                  │
 │     │                                          │   │                                     │   │                                       │   │                                   │
 │     └─► {appN}                                 │   ├─► app1                              │   ├─► app1                                │   ├─► app2                            │
 │          │                                     │   │   │                                 │   │   │                                   │   │   │                               │
 │          ├─► kustomization.yaml                │   │   └─► kustomization.yaml            │   │   └─► kustomization.yaml              │   │   └─► kustomization.yaml          │
 │          │                                     │   │                                     │   │                                       │   │                                   │
 │          ├─► helm-repository.yaml              │   ├─► app2                              │   ├─► app3                                │   ├─► app3                            │
 │          │                                     │   │   │                                 │   │   │                                   │   │   │                               │
 │          └─► helm-deployment.yaml              │   │   ├─► kustomization.yaml            │   │   ├─► kustomization.yaml              │   │   ├─► kustomization.yaml          │
 │                                                │   │   │                                 │   │   │                                   │   │   │                               │
 │                                                │   │   └─► values.yaml                   │   │   └─► values.yaml                     │   │   └─► values.yaml                 │
 │                                                │   │                                     │   │                                       │   │                                   │
 │                                                │   └─► kustomization.yaml                │   └─► kustomization.yaml                  │   └─► kustomization.yaml              │
 │                                                │                                         │                                           │                                       │
 │                                                └─► pro                                   └─► pro                                     └─► pro                                 │
 │                                                    │                                         │                                           │                                   │
 │                                                    ├─► app1                                  ├─► app1                                    ├─► app2                            │
 │                                                    │   │                                     │   │                                       │   │                               │
 │                                                    │   └─► kustomization.yaml                │   └─► kustomization.yaml                  │   └─► kustomization.yaml          │
 │                                                    │                                         │                                           │                                   │
 │                                                    ├─► app2                                  ├─► app3                                    ├─► app3                            │
 │                                                    │   │                                     │   │                                       │   │                               │
 │                                                    │   ├─► kustomization.yaml                │   ├─► kustomization.yaml                  │   ├─► kustomization.yaml          │
 │                                                    │   │                                     │   │                                       │   │                               │
 │                                                    │   └─► values.yaml                       │   └─► values.yaml                         │   └─► values.yaml                 │
 │                                                    │                                         │                                           │                                   │
 │                                                    └─► kustomization.yaml                    └─► kustomization.yaml                      └─► kustomization.yaml              │
 │                                                                                                                                                                              │
 │                                                                                                                                                                              │
 │                                                                                                                                                                              │
 └──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┘
```
