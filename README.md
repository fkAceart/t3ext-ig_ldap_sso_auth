## Extended version of ig_ldap_sso_aut.

# What is different?

The extension uses the objectGUID attribute of an ldap user to sync and fetch the users from ldap.
The objectGUID is set at the users typo3 database record and will be used with the highest priotity for matching users.
If the objectGUID can not be find at the users attributes it uses the dn and after that the username as a fallback mechanism.

# Why we need to use this?

The objectGUID attribute is unique and cannot be changed.
The extension uses the dn attribute as default validation value.
This value can be changed due the fact that it contains the users name.
As we want to update the user's attributes every night and synchronize the database values with the values from ldap, we need to use this value to avoid synchronizing malfunctions for users that change their names.
