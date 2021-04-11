# Zig distribution
ARG FROM
FROM $FROM

# Install zig
RUN MACHINE_ARCH="$(uname -m)" \
    && ZIG_VERSION="0.7.1" \
    && DIR_NAME="zig-linux-${MACHINE_ARCH}-${ZIG_VERSION}" \
    && ARCHIVE_NAME="${DIR_NAME}.tar.xz" \
    && curl --proto '=https' --tlsv1.2 -sSfO \
        "https://ziglang.org/download/${ZIG_VERSION}/${ARCHIVE_NAME}" \
    && tar -xJf "${ARCHIVE_NAME}" \
    && install -D -m777 "${DIR_NAME}/zig" "/usr/bin/zig" \
    && cp -r "${DIR_NAME}/lib" "/usr/lib/zig" \
    && cp -r "${DIR_NAME}/docs" "/usr/share/doc/zig" \
    && install -D -m644 "${DIR_NAME}/LICENSE" "/usr/share/doc/zig/LICENSE" \
    && rm -r "${DIR_NAME}"
