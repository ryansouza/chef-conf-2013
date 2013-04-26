## Cookbook Refactoring

##### Seth Vargo (Opscode)

### Refactoring /etc/hosts cookbook

- started with basic template, only the node's hostname
- changed to attribute array of hosts
    - allows other recipes, cookboooks, roles, environments to add hosts
    - painful finding a specific entry, its just attributes
    - attributes aren't validated or type checked
    - decided to move all attributes to databags, added tests
- data bags
    - just lines to be dropped in hosts file
    - added tests: confirmed given good data the recipe would work
    - no querying, not dynamic
    - cookbooks are not managing themselves
- basic lwrp
    - simple interface for cookbooks to use
    - rewrote the file on each run
    - provider kept growing, untested
- refactored lwrp
    - pure ruby file handling
    - extracted file handling to library
    - stateless provider, just proxies to library
    - same simple resource interface
- manipulator library
    - parsed hosts file
    - exposed add/remove/find host entries
    - tested with rspec
    - released as rubygem
    - use chef_gem to include gem as chef run


