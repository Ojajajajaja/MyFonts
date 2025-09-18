# MyFonts

Add this in your dockerfile to get these fonts

  

    RUN mkdir -p /usr/share/fonts/truetype/custom \
	    && mkdir -p /usr/share/fonts/opentype/custom \
	    && cd /tmp \
	    && curl -L -o MyFonts.zip https://github.com/Ojajajajaja/MyFonts/archive/refs/heads/main.zip \
	    && unzip MyFonts.zip \
	    && find MyFonts-main/ -type f \( -iname "*.ttf" -o -iname "*.otf" \) \
	    && find MyFonts-main/ttf -type f -iname "*.ttf" -exec cp {} /usr/share/fonts/truetype/custom/ \; \
	    && find MyFonts-main/otf -type f -iname "*.otf" -exec cp {} /usr/share/fonts/opentype/custom/ \; \
	    && fc-cache -fv \
	    && rm -rf /tmp/MyFonts.zip /tmp/MyFonts-main
