## coder schedule start

Edit workspace start schedule

### Synopsis

Schedules a workspace to regularly start at a specific time.
Schedule format: <start-time> [day-of-week] [location].

- Start-time (required) is accepted either in 12-hour (hh:mm{am|pm}) format, or 24-hour format hh:mm.
- Day-of-week (optional) allows specifying in the cron format, e.g. 1,3,5 or Mon-Fri.
  Aliases such as @daily are not supported.
  Default: \* (every day)
- Location (optional) must be a valid location in the IANA timezone database.
  If omitted, we will fall back to either the TZ environment variable or /etc/localtime.
  You can check your corresponding location by visiting https://ipinfo.io - it shows in the demo widget on the right.

```
coder schedule start <workspace-name> { <start-time> [day-of-week] [location] | manual } [flags]
```

### Examples

```
  - Set the workspace to start at 9:30am (in Dublin) from Monday to Friday:

      $ coder schedule start my-workspace 9:30AM Mon-Fri Europe/Dublin
```

### Options

```
  -h, --help   help for start
```

### Options inherited from parent commands

```
      --global-config coder   Path to the global coder config directory.
                              Consumes $CODER_CONFIG_DIR (default "~/.config/coderv2")
      --header stringArray    HTTP headers added to all requests. Provide as "Key=Value".
                              Consumes $CODER_HEADER
      --no-feature-warning    Suppress warnings about unlicensed features.
                              Consumes $CODER_NO_FEATURE_WARNING
      --no-version-warning    Suppress warning when client and server versions do not match.
                              Consumes $CODER_NO_VERSION_WARNING
      --token string          Specify an authentication token. For security reasons setting CODER_SESSION_TOKEN is preferred.
                              Consumes $CODER_SESSION_TOKEN
      --url string            URL to a deployment.
                              Consumes $CODER_URL
  -v, --verbose               Enable verbose output.
                              Consumes $CODER_VERBOSE
```

### SEE ALSO

- [coder schedule](coder_schedule.md) - Schedule automated start and stop times for workspaces
