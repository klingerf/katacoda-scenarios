If you glance at the Conduit dashboard, you should see all the HTTP/2 and HTTP/1-speaking services in the demo app show up in the list of deployments that have been added to the Conduit mesh.

View the demo app by visiting the web service’s public IP:

`minikube -n emojivoto service web-svc --url`{{execute}}

Finally, let’s take a look back at our dashboard (run conduit dashboard if you haven’t already). You should be able to browse all the services that are running as part of the application to view:

- Success rates
- Request rates
- Latency distribution percentiles
- Upstream and downstream dependencies

As well as various other bits of information about live traffic. Neat, huh?

Views available in `conduit dashboard`:

SERVICE MESH

Displays continuous health metrics of the control plane itself, as well as high-level health metrics of deployments in the data plane.

DEPLOYMENTS

Lists all deployments by requests, success rate, and latency.

Of course, the dashboard isn’t the only way to inspect what’s happening in the Conduit service mesh. The CLI provides several interesting and powerful commands that you should experiment with, including `conduit stat` and `conduit tap`.

To view details per deployment, run:

`conduit stat deployments`{{execute}}

To see a live pipeline of requests for your application, run:

`conduit tap deploy emojivoto/voting`{{execute}}