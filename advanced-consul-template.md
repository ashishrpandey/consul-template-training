
# Render multiple templates in the same process and invoke command on each change

The optional third argument to the template is a command that will execute each time the template changes.

      $ consul-template \
          -template "/tmp/nginx.ctmpl:/var/nginx/nginx.conf:nginx -s reload" \
          -template "/tmp/redis.ctmpl:/var/redis/redis.conf:service redis restart" \
          -template "/tmp/haproxy.ctmpl:/var/haproxy/haproxy.conf"
          

Query consul for services 

    {{ range service "web" }}
    server {{ .Name }} {{ .Address }}:{{ .Port }}{{ end }}

To get all the secrets on a PATH in Vault

      {{ secrets "<PATH>" }}

OR print it 

      {{ range secrets "secret/" }}
      {{ . }}{{ end }}


To iterate and list over every secret in the generic secret backend in Vault:

      {{ range secrets "secret/" }}
      {{ with secret (printf "secret/%s" .) }}{{ range $k, $v := .Data }}
      {{ $k }}: {{ $v }}
      {{ end }}{{ end }}{{ end }}
