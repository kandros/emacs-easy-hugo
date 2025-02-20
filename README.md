# easy-hugo [![melpa badge][melpa-badge]][melpa-link] [![melpa stable badge][melpa-stable-badge]][melpa-stable-link]

Emacs major mode for writing blogs made with hugo by markdown or org-mode or AsciiDoc or reStructuredText or mmark or html

## Screencast

![screencast](image/screencast.gif)

	M-x easy-hugo

You can manage blogs on easy-hugo-mode.

If you manage multiple blogs, you can switch blogs with the < or > key.

![easy-hugo-mode](image/easy-hugo-mode.png)

    M-x easy-hugo-newpost

You can post a new article.

Enter a article file name in the minibuffer.

A markdown file is automatically generated.

You can write a blog with markdown.

![easy-hugo4](image/easy-hugo4.png)

If you enter '.org' file name in the minibuffer, org file is automatically generated and you can write a blog with org-mode.

![easy-org-mode](image/org-mode.png)

If you enter '.ad' file name in the minibuffer, AsciiDoc file is automatically generated and you can write a blog with AsciiDoc.

![easy-org-mode](image/asciidoc.png)

If you enter '.rst' file name in the minibuffer, reStructuredText file is automatically generated and you can write a blog with reStructuredText.

![easy-org-mode](image/rst.png)

If you enter '.mmark' file name in the minibuffer, mmark file is automatically generated and you can write a blog with mmark.

![easy-org-mode](image/mmark.png)

If you enter '.html' file name in the minibuffer, html file is automatically generated and you can write a blog with html.

![easy-org-mode](image/html.png)

    M-x easy-hugo-preview

![screencast](image/screencast2.gif)

If your hugo version is 0.25 or higher, you can preview by following the edited part.

![easy-hugo6](image/easy-hugo6.png)
(The picture of the header is http://www.pixiv.net/member_illust.php?mode=medium&illust_id=60674880)

The browser opens automatically and you can preview the blog on your PC.

Even if you run the easy-hugo-preview command many times, only one hugo process will run so do not mind it.

Since the process of hugo running in the PC disappears in 300 seconds, you do not have to worry about killing hugo process.

    M-x easy-hugo-publish

You can publish your blog to the server and the browser opens automatically.

	M-x easy-hugo-helm-ag

![easy-hugo-helm-ag](image/easy-hugo-helm-ag.png)

You can search blog article with [helm-ag](https://github.com/syohex/emacs-helm-ag).

    M-x easy-hugo-article

Open the list of articles you wrote with dired.

	M-x easy-hugo-github-deploy

Execute deploy.sh which exists in directory `easy-hugo-basedir`.

It is useful for hosting on [GitHub Pages](https://gohugo.io/tutorials/github-pages-blog/) etc.

	M-x easy-hugo-amazon-s3-deploy

Deploy hugo source at Amazon S3.

	M-x easy-hugo-google-cloud-storage-deploy

Deploy hugo source at Google Cloud Storage.

	M-x easy-hugo-image

Generate link of image from image file directory under 'static' directory.

![easy-hugo-image1](image/easy-hugo-image1.png)

When you select the image file you want to use, a link will be inserted.

![easy-hugo-image2](image/easy-hugo-image2.png)

	M-x easy-hugo-put-image

Move image to 'easy-hugo-image-dirctory' and generate image link.

You can change the initial launch position with 'easy-hugo-default-picture-directory'.

![easy-hugo-put-image](image/easy-hugo-put-image.png)

	M-x easy-hugo-pull-image

Pull image from internet to image directory and generate image link.

Copy the URL of the image you want to download with your browser.

Execute M-x easy-hugo-pull-image.

![easy-hugo-pull-image](image/easy-hugo-pull-image.png)

Decide file name.

If you press enter without deciding the file name, the file name can be used as it is.

![easy-hugo-pull-image1](image/easy-hugo-pull-image1.png)

The file is saved in 'easy-hugo-image-dirctory' and generate image link.

![easy-hugo-pull-image2](image/easy-hugo-pull-image2.png)

## Commands for easy-hugo-mode

|key    |function      |
|-------|--------------|
|o		|easy-hugo-open|
|e      |easy-hugo-open|
|f		|easy-hugo-open|
|RET	|easy-hugo-open|
|<		|easy-hugo-previous-blog|
|>		|easy-hugo-next-blog|
|?		|describe-mode|
|A		|easy-hugo-amazon-s3-deploy|
|C		|easy-hugo-google-cloud-storage-deploy|
|D		|easy-hugo-list-draft|
|G		|easy-hugo-github-deploy|
|H		|easy-hugo-github-deploy-timer|
|I		|easy-hugo-google-cloud-storage-deploy-timer|
|i		|easy-hugo-cancel-google-cloud-storage-deploy-timer|
|N		|easy-hugo-no-help|
|O		|easy-hugo-open-basedir|
|P		|easy-hugo-publish|
|R		|easy-hugo-rename|
|S		|easy-hugo-sort-char|
|T		|easy-hugo-publish-timer|
|W		|easy-hugo-amazon-s3-deploy-timer|
|a		|easy-hugo-helm-ag|
|b		|easy-hugo-cancel-github-deploy-timer|
|c		|easy-hugo-open-config|
|d		|easy-hugo-delete|
|g		|easy-hugo-refresh|
|h		|easy-hugo-backward-char|
|j		|easy-hugo-next-line|
|k		|easy-hugo-previous-line|
|l		|easy-hugo-forward-char|
|m		|easy-hugo-cancel-amazon-s3-deploy-timer|
|n		|easy-hugo-newpost|
|p		|easy-hugo-preview|
|q		|easy-hugo-quit|
|r		|easy-hugo-refresh|
|s		|easy-hugo-sort-time|
|t		|easy-hugo-cancel-publish-timer|
|u		|easy-hugo-undraft|
|v		|easy-hugo-view|
|w		|easy-hugo-newpost|
|SPC	|easy-hugo-next-line|
|S-SPC	|easy-hugo-previous-line|
|←	    |easy-hugo-backward-char|
|→     |easy-hugo-forward-char|
|C-b	|easy-hugo-backward-char|
|C-f	|easy-hugo-forward-char|
|C-n	|easy-hugo-next-line|
|C-p	|easy-hugo-previous-line|
|M-b	|easy-hugo-backward-word|
|M-<	|easy-hugo-beginning-of-buffer|

## Requirements

- Emacs 24.4 or higher
- hugo 0.19 or higher

## Installation

You can install `easy-hugo.el` from [MELPA](http://melpa.org) with package.el
(`M-x package-install easy-hugo`).

## Sample Configuration

	(setq easy-hugo-basedir "~/bookshelf/")
	(setq easy-hugo-url "https://yourblogdomain")
	(setq easy-hugo-sshdomain "blogdomain")
	(setq easy-hugo-root "/home/blog/")
	(setq easy-hugo-previewtime "300")
	(define-key global-map (kbd "C-c C-e") 'easy-hugo)

easy-hugo-basedir "Directory where hugo html source code is placed on your PC."

easy-hugo-url "Url of the blog."

easy-hugo-sshdomain "Domain written in ~/.ssh/config."

easy-hugo-root "Root directory of hugo at your server."

easy-hugo-previewtime "Preview display time."

If you want deploy hugo at Amazon S3, please install AWS CLI and set easy-hugo-amazon-s3-bucket-name.

	(setq easy-hugo-amazon-s3-bucket-name "your-amazon-s3-bucket-name")

If you want deploy hugo at Google Cloud Storage, please install Google Cloud SDK and set easy-hugo-google-cloud-storage-bucket-name.

	(setq easy-hugo-google-cloud-storage-bucket-name "your-google-cloud-storage-bucket-name")

When writing blog with org-mode at .org file or rst-mode at .rst file or web-mode at .html file,
"C-c C-e" keys are duplicated so please use other keys.

If you want the default extension to be '.org'.

If not set the default extension will be '.md'.

	(setq easy-hugo-default-ext ".org")

If you want the default extension to be '.ad'.

If not set the default extension will be '.md'.

	(setq easy-hugo-default-ext ".ad")

If you want the default extension to be '.rst'.

If not set the default extension will be '.md'.

	(setq easy-hugo-default-ext ".rst")

If you want to change to No help-mode from startup

	(setq easy-hugo-no-help t)

If you want to set charactor-sort at s key.
If not set the default s key will be sort time.

	(setq easy-hugo-sort-default-char t)

If you want customise color, write the following in the init.el or .emacs.

	(defface easy-hugo-help-face
	'((((class color) (background light)) (:bold t :foreground "your-hex-color" :background "your-hex-color"))
    (((class color) (background dark)) (:bold t :foreground "your-hex-color" :background "your-hex-color")))
	""
	:group 'easy-hugo-faces)

In order to generate link of image from image file directory under 'static' directory,

If you want to change image file directory under 'static' directory.

If not set the default image file directory will be 'images'.

	(setq easy-hugo-image-dirctory "img")

Setting the picture directory of your PC, it is easy to execute M-x easy-hugo-put-image

	(setq easy-hugo-default-picture-directory "~/Pictures")

If you want to manage multiple blogs.

Example of setting when adding two blogs and managing a total of three blogs.

	;; Main blog
	(setq easy-hugo-basedir "~/bookshelf/")
	(setq easy-hugo-url "https://yourblogdomain")
	(setq easy-hugo-sshdomain "blogdomain")
	(setq easy-hugo-root "/home/blog/")
	(setq easy-hugo-previewtime "300")
	(define-key global-map (kbd "C-c C-e") 'easy-hugo)
	;; Total number of blogs
	(setq easy-hugo-blog-number 3)
	;; Blog1
	(setq easy-hugo-basedir-1 "~/src/github.com/masasam/ppap1/")
	(setq easy-hugo-url-1 "http://example1.com")
	(setq easy-hugo-root-1 "/home/blog/")
	(setq easy-hugo-sshdomain-1 "blog1domain")
	;; Blog2
	(setq easy-hugo-basedir-2 "~/src/github.com/masasam/ppap2/")
	(setq easy-hugo-url-2 "http://example2.com")
	(setq easy-hugo-amazon-s3-bucket-name-2 "blogbucket")

A total of until 10 blogs can be managed.

Please set necessary variables and use.

	easy-hugo-basedir-1
	easy-hugo-url-1
	easy-hugo-root-1
	easy-hugo-sshdomain-1
	easy-hugo-amazon-s3-bucket-name-1
	easy-hugo-google-cloud-storage-bucket-name-1
	easy-hugo-image-dirctory-1

	..............

	easy-hugo-basedir-9
	easy-hugo-url-9
	easy-hugo-root-9
	easy-hugo-sshdomain-9
	easy-hugo-amazon-s3-bucket-name-9
	easy-hugo-google-cloud-storage-bucket-name-9
	easy-hugo-image-dirctory-9

If you want change markdown filename extension, please select md or markdown or mdown.
Because only these three are supported by hugo. If not set markdown filename extension will be 'md'.

	(setq easy-hugo-markdown-extension "markdown")

If you want change asciidoc filename extension, please select ad or asciidoc or adoc.
Because only these three are supported by hugo. If not set asciidoc filename extension will be 'ad'.

	(setq easy-hugo-asciidoc-extension "asciidoc")

If you want change html filename extension, please select html or htm.
Because only these two are supported by hugo. If not set html filename extension will be 'html'.

	(setq easy-hugo-asciidoc-extension "htm")

Themes like [Cocoa-hugo-theme](https://github.com/nishanths/cocoa-hugo-theme) store its posts under content/blog.
Cocoa-hugo-theme user should add the following settings to init.el or .emacs.

	(setq easy-hugo-postdir "content/blog")

## Preparation for useing this package

Install hugo

See https://gohugo.io/

Quickstart Guide

See https://gohugo.io/overview/quickstart/

### Configuration file example

config.toml

	hasCJKLanguage = true
	theme="material-design"
	baseurl = "https://example.com"
	languageCode = "ja"
	title = "PPAP blog"
	MetaDataFormat = "toml"
	paginate = 9
	copyright = "© 2017 PPAP blog powered by Hugo"

	[params]
	blogurl = "https://example.com"
	blogdomain = "example.com"
	github = "your github user name"
	twitter = "your twitter user name"
	googleAnalyticsUserID = "UA-************"

	[permalinks]
	post = "/:year/:month/:day/:title/"

archetypes/default.md

	+++
	categories = [""]
	tags = [""]
	title = "{{ replace .TranslationBaseName "-" " " | title }}"
	date = "{{ .Date }}"
    draft = false
	+++

archetypes/default.org (If your hugo version is 0.25 or higher)

	+++
	categories = [""]
	tags = [""]
	title = "{{ replace .TranslationBaseName "-" " " | title }}"
	date = "{{ .Date }}"
    draft = false
	+++

archetypes/default.ad

	+++
	categories = [""]
	tags = [""]
	title = "{{ replace .TranslationBaseName "-" " " | title }}"
	date = "{{ .Date }}"
    draft = false
	+++

archetypes/default.rst

	+++
	categories = [""]
	tags = [""]
	title = "{{ replace .TranslationBaseName "-" " " | title }}"
	date = "{{ .Date }}"
    draft = false
	+++

archetypes/default.mmark

	+++
	categories = [""]
	tags = [""]
	title = "{{ replace .TranslationBaseName "-" " " | title }}"
	date = "{{ .Date }}"
    draft = false
	+++

archetypes/default.html

	+++
	categories = [""]
	tags = [""]
	title = "{{ replace .TranslationBaseName "-" " " | title }}"
	date = "{{ .Date }}"
    draft = false
	+++

### Prepare the server

Let's build with a free trial of "google compute engine" or "amazon ec2".

If you want deploy hugo at GitHub Pages or Amazon S3 or Google Cloud Storage, This paragraph is not necessary.

I created my blog in google compute engine.

Check if rsync is installed on the server.

Write at ~/.ssh/config on your PC

	 Host blogdomain
                        HostName "Your server's IP"
                        User "Your server's ssh login username"

Because blog is generated under /home/blog/ on the server, set it to reference it with nginx.
SSL uses certbot (Let's encrypt).

sample nginx.conf

	server {
		listen 80;
		server_name yourdomain;
		return  301 https://yourdomain$request_uri;
		location / {
			root /home/blog;
		index	index.html index.htm;
		}
	}
	server {
		listen 443;
		server_name yourdomain;
		ssl on;
		ssl_certificate      /etc/letsencrypt/live/yourdomain/fullchain.pem;
		ssl_certificate_key  /etc/letsencrypt/live/yourdomain/privkey.pem;

	location / {
		root    /home/blog;
	index   index.html index.htm;
		}
	}

Confirm that PATH passes from emacs to go.

I recommend you [exec-path-from-shell]( https://github.com/purcell/exec-path-from-shell).

Example without exec-path-from-shell

	(setenv "GOPATH" "~/go")
	(add-to-list 'exec-path (expand-file-name "~/go/bin"))

PPAP source sample

https://github.com/masasam/PPAP

[melpa-link]: http://melpa.org/#/easy-hugo
[melpa-badge]: http://melpa.org/packages/easy-hugo-badge.svg
[melpa-stable-link]: http://stable.melpa.org/#/easy-hugo
[melpa-stable-badge]: http://stable.melpa.org/packages/easy-hugo-badge.svg
