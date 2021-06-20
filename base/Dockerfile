FROM openjdk:11-jdk

ENV ARCHIVE_LINK=https://github.com/Kotlin/kotlin-interactive-shell/releases/download/v0.3.3/ki-archive.zip
ENV CHECKSUM=7d4c4356390e69387fd0eae8c4607b1f0111aac236df880c081bf40f903119e7
ENV INSTALL_ROOT=/opt
ENV INSTALL_DIR=$INSTALL_ROOT/ki
ENV LOCAL_DOWNLOAD_FILE_PATH=/opt/ki-archive.zip

RUN curl -L -o "$LOCAL_DOWNLOAD_FILE_PATH" "$ARCHIVE_LINK" 
RUN         echo "$CHECKSUM  $LOCAL_DOWNLOAD_FILE_PATH" | shasum -c 
RUN         unzip "$LOCAL_DOWNLOAD_FILE_PATH" -d "$INSTALL_ROOT"
RUN         chmod +x "$INSTALL_DIR/bin/ki.sh" 
RUN         chmod +x "$INSTALL_DIR/lib/ki-shell.jar" 

COPY bin /usr/local/bin

ENTRYPOINT /bin/bash



