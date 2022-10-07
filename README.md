# Concept points

There are 2 hosts involved:
 1. hcreator - localhost with ansible
 2. htarget - a remote host that is built and setup

Thus we only need one environment with those two hosts defined

Respectively there are two general stages in build flow.

Stage01 - to be run on creator for initiation: base image/ chroot /configs etc

Stage02 - to be run on target host when it is prepared on the stage 1 and up

Playbooks contain plays. Each play to be bound to either hcreator or htarget

Demo playbook consisting out of 2 Plays - one per stage. One Play per host.

Number of plays and stages can be extended within a playbook or by combining playbooks.

There are also 2 roles creator and target, to be assigned to hcreator and htarget

Base repo to be sufficient to get a generic result.

Each role contains an entry point for either of the stages. One entry per stage. Can be many though, if needed.

Each hook file is an ansible task file, (we may consider extending hook item to be a role, if task level proves to be insuficcient)

Hook files to be placed under hook dir into creator and target subdir.

A pair of creator and target subdirs represents customization of a project and kept in a separate repository.

Project repository itself therefore can/should only be used in conjunction with base repo. 

To be discussed



