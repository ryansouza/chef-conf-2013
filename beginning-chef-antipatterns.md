## Beginning Chef Antipatterns

##### Julian Dunn (Solutions Engineer at Opscode)


- best backed with real sys admin experience
    - advanced planning
    - having to refactor unplanned work expensive
- Plans:
    - naming convetions
    - cookbooks, recipes
    - roles, names, data bags
    - fuzzy idea of what environments look like

### Antipatterns

- single chef repo
    - cookbooks, data bags, roles, environments all together
    - temporal data(environments roles) tied with versioned (cookbook)
    - chef-data repo

- single giant cookbook, "your-company.git"
    - mixes unrelated code, ideas, responsibility
    - large "blast radius" of small changes

- over-using chef environments
    - should not be for "clusters" or "data-center"
    - think of above ahead of time, use them in search

- forking community cookbooks
    - don't get upstream bugfixes & updates
    - wrap community cookbook with yours, twiddles attrs?

- run list in roles
    - roles are temporal, not versioned
    - hard to deploy nicely?
    - make a roles cookbook instead?
    - ties in with normal cookbook deploying, versioning

- disorganized data bags
    - plan them from the start
    - only two levels of hierarchy, bag and its keys
    - don't just stuff it full of json

- not using chef-shell
    - debugging on production
    - development
    - very useful for accessing search?

- avoiding LWRP
    - they're not hard, you don't need that much ruby
    - just inline resources, basic ruby work

- not invented here syndrome
    - avoiding other code, cookbooks

- avoid being the only chef
    - sys-admins and devs should work together on cookbooks
