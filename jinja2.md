### Print the variable
``` jinja
{{ var }}
```
### if condition
``` jinja
{% 'true messsage' if var else 'false message' %}
```
> If var is `true` then print the true messsage otherwise failed message

``` jinja
{% if 'abc' == env %}
serverURL: '{{ server_abc }}'
{% elif 'def' == env %}
serverURL: '{{ server_def }}'
{% elif 'xyz' == env %}
serverURL: '{{ server_xyz }}'
{% else %}
ServerURL: 'server URL not found'
{% endif %}
```


### loop 
``` jinja
{% for var in vars %}
{{ var }}
{% endfor %}
```
> here the vars is the lsit or dictionary


### Setting the variable
``` jinja
{% set var = '123' %}
```
