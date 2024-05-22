MOD_ID := {{cookiecutter.mod_id}}

.PHONY: build clean install

build:
	rm -rf build
	mkdir -p build
	cp -rf * build/
	cd build && rm -rf $(cat .balamodignore | tr '\n' ' ') && rm -f .balamodignore && rm -rf $(cat .gitignore | tr '\n' ' ')
	cd build && find . -exec tar czvf $(MOD_ID) {} +

clean:
	rm -f $(MOD_ID).tar.gz
	rm -rf build

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
