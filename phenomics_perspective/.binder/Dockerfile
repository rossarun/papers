  
FROM rocker/binder:3.6.0
LABEL maintainer='Tyson Lee Swetnam'
USER root
RUN tlmgr init-usertree \
 && tlmgr update --self \
 && tlmgr install pgf environ placeins psnfss titlesec trimspaces palatino mathpazo setspace microtype xcolor fancyhdr ms
COPY . ${HOME}
RUN chown -R ${NB_USER} ${HOME}
USER ${NB_USER}

RUN wget https://raw.githubusercontent.com/genophenoenvo/papers/master/phenomics_perspective/DESCRIPTION && R -e "options(repos = list(CRAN = 'http://mran.revolutionanalytics.com/snapshot/2020-01-28/')); devtools::install_deps()"

RUN rm DESCRIPTION.1; exit 0
