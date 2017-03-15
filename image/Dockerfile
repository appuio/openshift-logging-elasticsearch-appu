FROM openshift/origin-logging-elasticsearch:latest

RUN \
  { \
    echo; \
    echo 'sg_role_monitoring:'; \
    echo '  users:'; \
    echo '    - system:serviceaccount:monitoring-infra:monitoring'; \
    echo; \
  } >> ${HOME}/sgconfig/sg_rolesmapping.yml && \
  { \
    echo; \
    echo 'sg_role_monitoring:'; \
    echo '  indices: {}'; \
    echo '  cluster:'; \
    echo '    - cluster:monitor/health'; \
    echo '    - cluster:monitor/nodes/info'; \
    echo '    - cluster:monitor/nodes/stats'; \
    echo; \
  } >> ${HOME}/sgconfig/sg_roles.yml

# vim: set sw=2 sts=2 et :
