CodeRed CMS Django Settings
===========================

Default settings are loaded from ``coderedcms/settings.py``. Available settings for CodeRed CMS:


CODERED_PROTECTED_MEDIA_ROOT
----------------------------

The directory where files from File Upload fields on Form Pages are saved. These files are
served through Django using ``CODERED_PROTECTED_MEDIA_URL`` and require login to access.
Defaults to ``protected/`` in your project directory.


CODERED_PROTECTED_MEDIA_URL
---------------------------
The URL for protected media files from form file uploads. Defaults to ``'/protected/'``


CODERED_PROTECTED_MEDIA_UPLOAD_WHITELIST
----------------------------------------

The allowed filetypes for media upload in the form of a list of file type extensions.
Default is blank. For example, to only allow documents and images, set to:
``['.pdf', '.doc', '.docx', '.txt', '.rtf', '.jpg', '.jpeg', '.png', '.gif']``


CODERED_PROTECTED_MEDIA_UPLOAD_BLACKLIST
----------------------------------------

The disallowed filetypes for media upload in the form of a list of file type extensions.
Defaults to ``['.sh', '.exe', '.bat', '.ps1', '.app', '.jar', '.py', '.php', '.pl', '.rb']``


CODERED_FRONTEND_*
------------------

Various frontend settings to specify defaults and choices used in the wagtail admin related
to rendering blocks, pages, and templates. By default, all CODERED_FRONTEND_* settings are
designed to work with Bootstrap 4 CSS framework, but these can be customized if using a
different CSS framework or theme variant.

.. warning::
    CODERED_FRONTEND_* settings are experimental and are known to cause issues
    with migrations. If you do need to use them:

    * DO NOT run ``makemigrations`` or ``makemigrations coderedcms``
    * ONLY run migrations for specific apps, i.e. ``makemigrations website``
