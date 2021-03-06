An extension of The [Kohana 3 Auth module](http://github.com/kohana/auth) for use with [Sprig](http://github.com/shadowhand/sprig) User models.

This module must be added to the active modules array in your bootstrap BEFORE auth module as it overrides some classes.

### Incompatibilities with Auth ORM driver

1.    There is one intentional difference from the ORM driver for Auth module, and that is that logged_in() (and by extension get_user()) will automatically call auto_login() if no user session is found. This functionality seems the most sensible to me. If this causes problems for you please raise it as an issue or just override Auth_Sprig and change it back.

### Known Issues

1.    Role checking doesn't work as expected when the user object is retrived from the session as Sprig uses Mysql Result objects. Need to investigate how to make this work correctly.
	(This relates to Sprig [issue 40](http://github.com/shadowhand/sprig/issues/#issue/40) and Kohana Database [issue 2297](http://dev.kohanaphp.com/issues/2297) and is temporarily fixable by [this branch](http://github.com/banks/sprig/tree/serializable) in my sprig fork. 