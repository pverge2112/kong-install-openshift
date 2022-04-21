Installing Kong Gateway on Red Hat OpenShift
===========================================================

This example stands up a Kong Gateway instance on a pre-provisioned instance of OpenSgift, using Kong Ingress Controller (KIC) for proxying service calls and HAProxy as Ingress Controller.  This way, we can leverage OpenShift Routes to proxy requests into kong-manager, admin-api and dev-portal.  Lastly, we enable OIDC RBAC for Kong Manager and Developer Portal and configure Okta as the IdP.

## Prerequisites
1. An OpenShift instance up and running and access to a `cluster-admin` user.
3. `oc` CLI

## Procedure

1. Copy your enterprise license file to a new file called `license`.

2. Run the install script via a BASH shell, passing the `.apps.*` part or your OpenShift cluster URL e.g. `.apps.pvergilis-rosa.ukwh.p1.openshiftapps.com`:

```bash
./install.sh <apps URL>
```

3. Login to Kong Manager with `http://manager-kong.<apps URL>` (u: kong_admin p: kong)

4. Kong Dev Portal can be reached at `http://dev-portal.<apps URL>` once Dev Portal has been enabled via the Manager.

5. API requests can be posted to `proxy-kong.<apps URL>`.