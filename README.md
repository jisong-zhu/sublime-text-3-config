sublime-text-3-config
=====================

Configuration for sublime text 3 and some useful packages, only for linux.

###Package control

Using ``` ctrl+` ``` to call out command line and paste following code.
```python
import urllib.request,os,hashlib; h = '7183a2d3e96f11eeadd761d777e62404e330c659d4bb41d3bdf022e94cab3cd0'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by) 
```
By the way, sublime text2 paste:
```python
import urllib2,os,hashlib; h = '7183a2d3e96f11eeadd761d777e62404e330c659d4bb41d3bdf022e94cab3cd0'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); os.makedirs( ipp ) if not os.path.exists(ipp) else None; urllib2.install_opener( urllib2.build_opener( urllib2.ProxyHandler()) ); by = urllib2.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); open( os.path.join( ipp, pf), 'wb' ).write(by) if dh == h else None; print('Error validating download (got %s instead of %s), please try manual install' % (dh, h) if dh != h else 'Please restart Sublime Text to finish installation') 
```

###Basic settings

```json
{
    "folder_exclude_patterns": [
        ".svn",
        ".git",
        ".hg",
        "CVS"
    ],
    "font_size": 12,
    "highlight_line": true,
    "ignored_packages": [
        "Vintage"
    ],
    "translate_tabs_to_spaces": true,
    "word_wrap": "true"
}
```

###Settings for JSFormat

```json
{
    // exposed jsbeautifier options
    "indent_with_tabs": false,
    "preserve_newlines": true,
    "max_preserve_newlines": 4,
    "space_in_paren": false,
    "jslint_happy": false,
    "brace_style": "collapse",
    "keep_array_indentation": true,
    "keep_function_indentation": false,
    "eval_code": false,
    "unescape_strings": false,
    "break_chained_methods": false,

    // jsformat options
    "format_on_save": true
}
```

###Common package

```text
JSFormat
LESS
Jade
Terminal
BracketHightlighter
SidebarEnhancements
```

###Input Chinese
Refer to [input Chinese in Sublime text 3](http://learninginfree.blogspot.com/2013/11/sublime-text-3-ubuntu.html)

1. Download sublime-imfix.so to your sublime installation dir, such as "/opt/sublime_text/sublime-imfix.so"
2. Edit sublime_text.desktop, such as "/usr/share/applications/sublime_text.desktop"

```
[Desktop Entry][...]Exec=env LD_PRELOAD=/opt/sublime_text/sublime-imfix.so /opt/sublime_text/sublime_text %F[...] 
[Desktop Action Window][...]Exec=env LD_PRELOAD=/opt/sublime_text/sublime-imfix.so /opt/sublime_text/sublime_text -n[...] 
[Desktop Action Document][...]Exec=env LD_PRELOAD=/opt/sublime_text/sublime-imfix.so /opt/sublime_text/sublime_text --command new_file[...]
```

<strong>NOTE:</strong> This is based on fcitx input method. You can refer to [Install Sogou Pinyin for Ubuntu](http://7071976.blog.51cto.com/7061976/1243471)
