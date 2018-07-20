build:
	rm -rf docs
	gitbook build
	mv _book docs
	git add .
	git commit -m "Build to GitHub"
	git push origin master
