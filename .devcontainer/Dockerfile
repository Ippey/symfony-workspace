ARG VARIANT=8-bullseye
FROM mcr.microsoft.com/vscode/devcontainers/php:${VARIANT}

# [Choice] Node.js version: none, lts/*, 16, 14, 12, 10
ARG NODE_VERSION="16"
RUN if [ "${NODE_VERSION}" != "none" ]; then su vscode -c "umask 0002 && . /usr/local/share/nvm/nvm.sh && nvm install ${NODE_VERSION} 2>&1"; fi

COPY --from=composer /usr/bin/composer /usr/bin/composer

RUN docker-php-ext-enable xdebug

RUN curl -1sLf 'https://dl.cloudsmith.io/public/symfony/stable/setup.deb.sh' | bash
RUN apt install -y symfony-cli \
                sqlite3
