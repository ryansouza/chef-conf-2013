# LDAP: Original use case

- testing adding ldap to chef server
- cucumber is hard, drifting specs is hard
- specific environment setups, specific architecture

# Test Kitchen

- declarative, simple, chef & erlang
- vms and remote instances
- travis for platforms
- (can it be part of automated ci? real boxes needed for vms?)

## Test kitchen goes public

- best way to test a cookbook works is run against instances
- doing it by hand sucks
- what people wanted to test:
  - across platforms
  - regressions
  - linting, unit testing
  - functional/integration, does it actually actual work
  - automated ci, jenkins
- limitations
  - new providers(non-vagrant?)
  - ruby *file dsls on dsls

(could we use this at EY to test random cluster setups?)

# Jamie CI

- rvm cookbook
  - large complex
  - building rubys as a test takes long time
- fast, small, external dependencies
- platform
  - os, networking, virtualization, chef version
- suite (chef configuration)
  - run list, attrs, name
- instance
- drivers
  - ship as rubygems

