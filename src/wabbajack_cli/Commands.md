# Wabbajack CLI

Wabbajack offers a command line interface with the following commands. To invoke the CLI, click on the settings cog on the top right of the Wabbajack UI and select "Open Terminal and Close WJ".

```
Usage:
  wabbajack-cli [command] [options]

Options:
  --version       Show version information
  -?, -h, --help  Show help and usage information

Commands:
  compile                         Compiles a modlist
  decrypt                         Decrypts a file from the wabbajack encrypted storage
  download-all                    Downloads all files for all modlists in the gallery
  download-url                    Downloads a file to a given output
  dump-zip-info                   Dumps the contents of a zip file to the console, for use in debugging wabbajack
                                  files
  encrypt                         Encrypts a file and stores it in the Wabbajack encrypted storage
  extract                         Extracts the contents of an archive into a folder
  force-heal                      Creates a patch from New file to Old file and uploads it
  hash-file                       Hashes a file with Wabbajack's hashing routines
  hash-url-string                 Hashes a URL string and returns the hashcode as hex
  install                         Installs a wabbajack file
  install-compile-install-verify  Installs a modlist, compiles it, installs it again, verifies it
  list-creation-club-content      Lists all known creation club content
  list-games                      Lists all games Wabbajack recognizes, and their installed versions/locations (if
                                  any)
  list-modlists                   Lists all known modlists
  mirror-file                     Mirrors a file to the Wabbajack CDN
  modlist-report                  Generates a usage report for a Modlist file
  steam-download-file             Dumps information to the console about the given app
  steam-app-dump-info             Dumps information to the console about the given app
  steam-login                     Logs into Steam via interactive prompts
  upload-to-nexus                 Uploads a file to the Nexus defined by the given .json definition file
  validate-lists                  Gets a list of modlists, validates them and exports a result list
  verify-modlist-install          Verify a modlist installed correctly
  vfs-index                       Index and cache the contents of a folder
```
