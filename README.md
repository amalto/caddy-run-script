# caddy-run-script

Inline javascript execution for Caddy V2 using the otto javascript interpreter: https://github.com/robertkrimen/otto

A small DSL would be required to alow a script to execute within a given Caddy context.

The DSL would consist of a few limited functions prefixed with `caddy_`.

### - Work In Progress -

Please feel free to comment by raising issues

#### Example
```
run_script {
"
const baseUrl = new URL(caddy_getPlaceHolder("http.request.uri.query.baseUrl"))
caddy_setPlaceHolder("vars.baseurl.pathname", baseUrl.pathname)
caddy_setPlaceHolder("vars.baseurl.hostname", baseUrl.hostname)
"
}
```
