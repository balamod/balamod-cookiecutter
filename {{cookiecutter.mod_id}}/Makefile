MOD_ID = {{cookiecutter.mod_id}}

.PHONY: build clean install

build:
	tar czvf $(MOD_ID).tar.gz main.lua assets localization manifest.json

clean:
	rm -f $(MOD_ID).tar.gz

install:
	if [ uname -s = "Darwin" ]; then \
		ln -s . "$HOME/Library/Application Support/Balatro/mods/{{cookiecutter.mod_id}}" \
	else if [ uname -s = "Linux" ]; then \
		ln -s . "$HOME/.local/share/Balatro/mods/{{cookiecutter.mod_id}}" \
	else if [ uname -s = "Windows_NT" ]; then \
		mklink /D "%APPDATA%/Balatro/mods/{{cookiecutter.mod_id}}" . \
	else \
		echo "Unknown OS" \
		exit 1 \
	fi \
