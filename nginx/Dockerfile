# prod
FROM nginx:1.25 as production-stage
COPY nginx/prod.conf /etc/nginx/nginx.conf
COPY backend/static /usr/src/app/static/
COPY dist/ /dist/
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]