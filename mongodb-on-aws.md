## Managing MongoDB Clusters on AWS with Chef

Charity Majors (Systems Engineer at Parse)

- backup
    - ebs snapshots, no snaplock?
    - mongodump (its not great?)
    - maybe only run ebs on a snapshot node
- provisioning
    - from a snapshot: good
    - secondary sync: alright
    - mongorestore: not great
- periodic secondary sync
    - compacts and repairs collections and dbs
    - hard on your primary
    - resets padding factor for all collections to 1
- RAID
    - deciding volume count is hard later, decide early
    - use piops
- mongodb::backups
    - cron job on backup host, NOT PRIMARY
    - ec2-consistent-snapshot of :mongo_volumes
    - locks db
- arbiters
    - processes that only vote
- snapshots
    - often
    - backup node should be priority 0, hidden 1
    - if you've got extra arbiters remove backup node from voting
    - run continuous compaction
- fragmentation
    - underuse of memory
    - deletes not the only source
    - fix by resync, repair, or compaction
- db.touch to warm up secondaries?
- mms monitoring
    - 10gen hosted solution
    - single python script
    - pretty
