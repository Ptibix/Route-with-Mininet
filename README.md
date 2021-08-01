
## What are you going to learn?

- How does routing logic work
- How to read a routing table using the `route` or the `ip route` commands
- How to view a host's assigned IP or IPs using `ip addr`
- How `ping` works
- How `traceroute` works
- What is a *hop*
- What is a *gateway*
- What are directly connected networks
- What is static routing
- What is dynamic routing (compared to static routing)

## Tasks

1. Grab and start a VM image pre-loaded with Mininet.
    - [Downloaded and started VM image containing Mininet from here](https://github.com/CodecoolBase/short-admin-vms/releases/latest/download/ubuntu-18.04-mininet.ova)
    - A shared folder is created between host and guest, the starter code is accessible from within the guest

2. Run `./mn.py` as `root` and note down your random network seed identifier.
    - Run `./mn.py` without any arguments and noted the down seed number from its output, e.g. 3070 in the following case

```
# ./mn.py
*** Using seed: 3070
mininet>
```
    - The same generated seed is used in every other tasks

3. Connect the `n1` and `n3` networks by configuring routing tables on the required nodes.
    - All hosts in `n1` can ping all hosts in `n3`
    - All hosts in `n3` can ping all hosts in `n1`
    - `task1.ini` contains the required routing commands
    - Running `./mn.py --task 1 --test --seed <your-seed>` outputs `Results: 0% dropped`

4. Connect the `n2` and `n3` networks by configuring routing tables on the required nodes.
    - All hosts in `n2` can ping all hosts in `n3`
    - All hosts in `n3` can ping all hosts in `n2`
    - `task2.ini` contains the required routing commands
    - Running `./mn.py --task 2 --test --seed <your-seed>` outputs `Results: 0% dropped`

5. Connect the `n2` and `n5` networks by configuring routing tables on the required nodes.
    - All hosts in `n2` can ping all hosts in `n5`
    - All hosts in `n5` can ping all hosts in `n2`
    - `task3.ini` contains the required routing commands
    - Running `./mn.py --task 3 --test --seed <your-seed>` outputs `Results: 0% dropped`

6. Connect the `n3` and `n5` networks by configuring routing tables on the required nodes.
    - All hosts in `n3` can ping all hosts in `n5`
    - All hosts in `n5` can ping all hosts in `n3`
    - `task4.ini` contains the required routing commands
    - Running `./mn.py --task 4 --test --seed <your-seed>` outputs `Results: 0% dropped`

7. Connect the `n1`, `n2` and `n4` networks by configuring routing tables on the required nodes.
    - All hosts in `n1` can ping all hosts in `n2` and `n4`
    - All hosts in `n2` can ping all hosts in `n1` and `n4`
    - All hosts in `n4` can ping all hosts in `n1` and `n2`
    - `task5.ini` contains the required routing commands
    - Running `./mn.py --task 5 --test --seed <your-seed>` outputs `Results: 0% dropped`

## General requirements

- Test `.txt` files are not modified, e.g. `test1.txt`, `test2.txt`, etc.
- `mn.py` is not modified
- Each task `.ini` file e.g. `task1.ini`, `task2.ini`, etc. should contain a comment with the seed used, e.g

```
# seed=1234
r1 ip add route ...
```