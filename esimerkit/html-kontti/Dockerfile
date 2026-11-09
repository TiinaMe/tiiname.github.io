# Pohjakuva: kevyt nginx-webpalvelin (Alpine Linux, n. 20 MB)
FROM nginx:alpine

# Kopioidaan omat sivut nginxin oletushakemistoon kontin sisälle
COPY sivut/ /usr/share/nginx/html/

# nginx kuuntelee porttia 80 kontin sisällä (dokumentaatiota varten)
EXPOSE 80
