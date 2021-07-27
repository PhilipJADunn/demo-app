
FROM 658251713809.dkr.ecr.eu-west-2.amazonaws.com/layer:latest AS layer

# Layer code

WORKDIR /opt

FROM public.ecr.aws/lambda/nodejs:14

COPY app.js package.json ./

RUN npm install

# Command can be overwritten by providing a different command in the template directly.
CMD ["app.lambdaHandler"]

FROM layer AS layer2
COPY --from=layer /opt/ .
