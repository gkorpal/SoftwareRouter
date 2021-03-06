**Group members:**  Caleb Dahlke and Gaurish Korpal 
 
**Description:** Implement PWOSPF dynamic routing.

**Resources used:**

0. Project description document
1. [POSIX thread (pthread) libraries](https://www.cs.cmu.edu/afs/cs/academic/class/15492-f07/www/pthreads.html)
2. Various StackOverflow posts
3. More specific sources cited within the code.

**Changes made to the [stub code](https://github.com/gkorpal/pwospf):**

* `sr_vns_comm.c`   :   include `sr_pwospf.h` header file in line 44;

* `sr_router.c`     :   edited `sr_handlepacket` function to incorporate the Hello and LSU packets;
                        edited `sr_handleForward` to incorporate dynamic routing when forwarding packets;
                    
* `sr_pwospf.c/h`   :  added the required header files; 
                       added data structures needed for the pwospf subsystem;
                       initialized the pwospf subsystem;
                       added methods needed for handling Hello and LSU packets;
                       implemented breadth-first search (BFS) for finding the shortest path;

**Functionalities available:**

0.  All the functionalities from the [previous project](https://github.com/gkorpal/ComputerNetworks/tree/master/simple-router) are still available.
1.  The routers are able to start with empty routing tables and converge to the shortest paths.
2.  After bringing one link down, the routers can detect it and converge to the new shortest path.
3.  After the link is brought back up, the routers detect it and converge to the original shortest paths.
4.  All routers do sanity check on packets (IP/OSPF version, IP/Hello/LSU/ICMP checksum, OSPF area ID and auth code).
