(require 'package) ;; You might already have this line
(add-to-list 'package-archives
             '("melpa" . "https://melpa.org/packages/"))
(when (< emacs-major-version 24)
  ;; For important compatibility libraries like cl-lib
  (add-to-list 'package-archives '("gnu" . "http://elpa.gnu.org/packages/")))
(package-initialize) ;; You might already have this line
(custom-set-variables
 ;; custom-set-variables was added by Custom.
 ;; If you edit it by hand, you could mess it up, so be careful.
 ;; Your init file should contain only one such instance.
 ;; If there is more than one, they won't work right. 
 '(wakatime-cli-path "/home/devcrack/Repositories/wakatime/wakatime/cli.py"))

(custom-set-faces
 ;; custom-set-faces was added by Custom.
 ;; If you edit it by hand, you could mess it up, so be careful.
 ;; Your init file should contain only one such instance.
 ;; If there is more than one, they won't work right.
 '(cursor ((t (:background "magenta")))))


(show-paren-mode 1)

(when (require 'wakatime-mode nil t)  
  (setq wakatime-api-key "7ca6b2cb-14e2-455f-be32-f9f3a7213d17")  
  ;; すべてのバッファで訪問時に記録を開始  
  (global-wakatime-mode)  
  )


; start auto-complete with emacs
(require 'auto-complete)


(require 'auto-complete-config)
(ac-config-default)

(require 'yasnippet)
(yas-global-mode 1)


; let's define a function which initializes auto-complete-c-headers and gets called for c/c++ hooks

(defun my:ac-c-header-init ()
  (require 'auto-complete-c-headers)
  (add-to-list 'ac-sources 'ac-source-c-headers)
  (add-to-list 'achead:include-directories '"/usr/lib/gcc/x86_64-linux-gnu/5/include")
  )

; now let's call this function from c/c++ hooks
(add-hook 'c++-mode-hook 'my:ac-c-header-init)
(add-hook 'c-mode-hook 'my:ac-c-header-init)

(desktop-save-mode 1)
;; Window number mode
;; First of all you have to install window-number package from melpa
;; And then add this lines 
(add-to-list 'load-path "~/.emacs.d/elpa/")
;; Load the package number-mode
(load "window-number")
;; Star the window-number mode
(window-number-mode 1)
;;Define keybinding for swith between buffers
(global-set-key(kbd "C-x n") 'window-number-switch) ;Ctrl + x Ctrl + n
;; (global-set-key(kbd "C-M ;") 'uncomment-region) ;Ctrl + x Ctrl + n
