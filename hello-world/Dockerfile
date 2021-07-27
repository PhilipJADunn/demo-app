FROM 658251713809.dkr.ecr.eu-west-2.amazonaws.com/layer:latest AS layer

# Layer code
WORKDIR /opt
COPY --from=layer /opt/ .

FROM public.ecr.aws/lambda/nodejs:14

# Function code
COPY app.js package.json ./
RUN npm install
CMD ["app.lambdaHandler"]
