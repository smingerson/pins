# auth='auto' picks appropriate method and error if none found

    Code
      check_auth()
    Error <rlang_error>
      auth = `auto` has failed to find a way to authenticate
      * Can't find CONNECT_SERVER and CONNECT_API_KEY envvars for `auth = 'envvar'`
      * Can't find any rsconnect::accounts() for `auth = 'rsconnect'`

# delivers useful messages if can't find RSC account

    Code
      rsc_server_rsconnect()
    Error <rlang_error>
      No RStudio Connect servers have been registered

---

    Code
      rsc_server_rsconnect()
    Error <rlang_error>
      Found multiple matching RStudio Connect servers
      i Please disambiguate with `server` and/or `account`

# auth is hidden

    Code
      server <- rsc_server_envvar("http://example.com", "SECRET")
      server$auth
    Output
      <hidden>
    Code
      str(list(1, server$auth, 2))
    Output
      List of 3
       $ : num 1
       $ : <hidden>
       $ : num 2

