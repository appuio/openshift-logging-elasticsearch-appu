FROM openshift/origin-logging-elasticsearch:latest

RUN \
  set -e && \
  \
  # Origin
  dest="${HOME}/sgconfig/sg_rolesmapping.yml" && \
  \
  # Container Platform
  if test -e "${HOME}/sgconfig/sg_roles_mapping.yml"; then \
    dest="${HOME}/sgconfig/sg_roles_mapping.yml"; \
  fi && \
  \
  { \
    echo; \
    echo 'sg_role_monitoring:'; \
    echo '  users:'; \
    echo '    - system:serviceaccount:monitoring-infra:monitoring'; \
    echo; \
  } >> "$dest" && \
  \
  { \
    echo; \
    echo 'sg_role_monitoring:'; \
    echo '  indices: {}'; \
    echo '  cluster:'; \
    echo '    - cluster:monitor/health'; \
    echo '    - cluster:monitor/nodes/info'; \
    echo '    - cluster:monitor/nodes/stats'; \
    echo; \
  } >> "${HOME}/sgconfig/sg_roles.yml"

# vim: set sw=2 sts=2 et :
