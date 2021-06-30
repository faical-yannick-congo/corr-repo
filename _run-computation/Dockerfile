## UniMarket REST API micro-service.
ARG tag
FROM unipay.azurecr.io/un1pay-generic-api:$tag

USER un1pay
WORKDIR /home/un1pay

COPY requirements.yml /home/un1pay/identity-requirements.yml
COPY startup.sh /home/un1pay/app-startup.sh

RUN /home/un1pay/anaconda/bin/conda env update -n un1pay --file /home/un1pay/identity-requirements.yml

## Executing the services.
CMD bash /home/un1pay/app-startup.sh

# export tag='dev'
# echo $tag
# docker build --build-arg tag=$tag -t un1pay-identity:$tag .
#
