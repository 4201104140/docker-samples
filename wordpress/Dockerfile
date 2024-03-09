ARG tag=php8.1-apache
FROM wordpress:${tag} AS custom

WORKDIR /usr/src/wordpress
COPY custom-theme/ ./wp-content/themes/custom-theme/
COPY custom-plugin/ ./wp-content/plugins/custom-plugin/

FROM wordpress:${tag} AS final
WORKDIR /usr/src/wordpress
RUN set -eux; \
	find /etc/apache2 -name '*.conf' -type f -exec sed -ri -e "s!/var/www/html!$PWD!g" -e "s!Directory /var/www/!Directory $PWD!g" '{}' +; \
	cp -s wp-config-docker.php wp-config.php
COPY --from=custom /usr/src/wordpress/wp-content/themes/custom-theme/ ./wp-content/themes/custom-theme/
COPY --from=custom /usr/src/wordpress/wp-content/plugins/custom-plugin/ ./wp-content/themes/plugins/custom-plugin/

# WORKDIR /var/www

# COPY entrypoint.sh /entrypoint.sh
# COPY common.sh /common.sh

# ENTRYPOINT [ "/entrypoint.sh" ]

# CMD [ "php-fpm" ]
