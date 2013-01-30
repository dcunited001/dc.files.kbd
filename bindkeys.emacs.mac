;;; bindings.emacs.el --- Key Bindings for Emacs
;;
;; Copyright (c) 2013 David Conner
;;
;; Author: David Conner <dconner.pro@gmail.com>
;; URL:
;; Version: 0.0.1
;; Keywords: me

;;; Commentary:

;; Mappin' some keys, boss.

;;; License:

;; Go on and map some keys, bubb.

;;; Code:

;; Codin' it on up now, boss.

;;==============================;;
;; Text
;;==============================;;
(global-set-key (kbd "\C-x w") 'wrap-no-lines)

;;==============================;;
;; Hyper Key
;;==============================;;
; http://stackoverflow.com/questions/10730775/emacs-create-key-modifier
; (define-key function-key-map (kbd "C-c H") 'event-apply-hyper-modifier)

; modifier keys can also be configured using these:
; (setq mac-option-modifier 'meta)
; (setq mac-control-modifier 'ctrl)
; (setq mac-command-modifier 'hyper)
; (setq mac-command-modifier 'super)
; (setq mac-command-key-is-meta  t)
; (setq mac-option-key-is-meta nil)
; (setq mac-command-key-is-meta t)
; (setq mac-option-modifier nil)

;;==============================;;
;; Buffers/Frames/Windows
;;==============================;;
(global-set-key "\M-`" 'next-multiframe-window)

;;==============================;;
;; My Key Bindings
;;==============================;;
;; http://es.gnu.org/~aleksander/emacs/dotemacs.el

; ;; Simplify Go-to-line with Meta-g
; (global-set-key "\M-g" 'goto-line)

; ;; C-c i calls insert-date-string
; (global-set-key (kbd "C-c i") 'insert-date-string)

; ;; Electric buffer list
; (global-set-key "\C-b" 'electric-buffer-list)
; (global-set-key "\C-x\C-b" 'electric-buffer-list)

; ;; Reload .emacs
; (global-set-key "\M-r"
;   '(lambda ()
;      (interactive)
;      (load-file "~/.emacs")))

; ;; disable that minimize window thing
; (global-unset-key "\C-x\C-z")

; ;; disable closing emacs in Mac OS X
; (if (system-type-is-darwin)
;     (global-unset-key "\C-z"))

; ;; Uncomment region command. Comment region is already "C-c c"
; (global-set-key (kbd "\C-c z") 'uncomment-region)

; ;; Enable Dired Extra
; (add-hook 'dired-load-hook
;           (lambda ()
;             (load "dired-x")))
