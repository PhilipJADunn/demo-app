FROM public.ecr.aws/lambda/nodejs:14

COPY app.js package.json ./

RUN npm install

# Command can be overwritten by providing a different command in the template directly.
CMD ["app.lambdaHandler"]

FROM public.ecr.aws/x0k1v7v4/image/magick/base:latest AS shared-lib-layer

# Layer code

WORKDIR /opt

COPY --from=shared-lib-layer /opt/ .
