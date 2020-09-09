ARG ELK_VERSION

# https://www.docker.elastic.co/
FROM docker.elastic.co/elasticsearch/elasticsearch:${ELK_VERSION}

ARG ELK_VERSION

ARG INSTALL_ANALYSIS_ICU=false

# Add your elasticsearch plugins setup here
# Example: RUN elasticsearch-plugin install analysis-icu
RUN if [ ${INSTALL_ANALYSIS_ICU} = true ]; then \
    elasticsearch-plugin install analysis-icu \
;fi

ARG INSTALL_ANALYSIS_IK=false
RUN if [ ${INSTALL_ANALYSIS_IK} = true ]; then \
    bin/elasticsearch-plugin install --batch "https://github.com/medcl/elasticsearch-analysis-ik/releases/download/v${ELK_VERSION}/elasticsearch-analysis-ik-${ELK_VERSION}.zip" \
;fi