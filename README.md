# Multi-threaded INET Framework for V2X Communications

This is multi-threaded version of INET Framework. Our implementation is able to reduce the simulation time, ensuring seamless integration with the existing scenarios of a user. This code is based on the legacy INET Framework (ver. 3.6.4-394571f) and is modified accordingly. INET Framework is an open-source suite for wired, wireless, and mobile networks.

For our research purposes, we modified the functions below:
* *visitObject* in the *PhysicalEnvironment* class.
* *visit* in the *DielectricObstacleLoss* class.

We also introduced the notion of the *distanceBoundary* under within the *ScalarAnalogueModel* class.
For further details about our modifications, please refer to ADD LINK.

# Licence

If this code is used for drafting a manuscript, the authors should cite the following paper:
```    
@inproceedings{multithreadedINET,
        author = {{Mavromatis}, I. and {Tassi}, A. and {Piechocki}, R.~J. and {Nix}, A.},
        title = {{Parallel Implementation of the OMNeT++ INET Framework for V2X Communications}},
        booktitle={Proc. of IEEE Vehicular Networking Conference (VNC) 2018},
        year = 2018,
        month = dec,
        pages={},
        doi={},
        ISSN={},
    }
```
# Requirements

The code is compatible with Linux (Ubuntu 16.04 LTS) and OS X 10.12 and 10.13. It is also compatible with Omnet++ 5.2.1 and Veins 4.6. The SUMO Traffic Generator (ver. 0.30.0) is required to generate the vehicle routes. All the above tools should be pre-installed. Please refer to the links below for detailed guides of how to install them.

For information about how to use Veins with INET and Omnet++, please refer to Veins_INET sub-module ([website](http://veins.car2x.org/documentation/modules/)).

# How to Use it
1. Our *Multi-threaded INET* project should be imported in Omnet++. For more information, please refer to Omnet++ Documententation.
    - Ensure that no other version of the INET Framework is opened in Omnet++.
2. The *Multi-threaded INET* project should be later compiled (Build Project in Omnet++).
3. Veins and Veins_INET projects should be imported in Omnet++ and compiled as well.
4. At the omnetpp.ini, please add the following lines:
```
Scenario.physicalEnvironment.numberOfThreads = 4
Scenario.radioMedium.analogModel.distanceBoundary = 1000
```
5. The *Scenario* is the name of the network to be simulated in Omnet++. The *numberOfThreads* can be modified accordingly to the machine used (please refer to our paper for more information and the difference in the performance introduced). Finally, the *distanceBoundary* can be modified with regard the scenario and the granularity required from the user.

# Useful Links
More information about Veins vehicular network simulation framework can be found in [Veins website](http://veins.car2x.org/).
More information about the INET Framework can be found in [INET Framework's website](https://inet.omnetpp.org/).
More information about Omnet++ can be found in [Omnet++ website](https://omnetpp.org/) and under the [documentation](https://omnetpp.org/documentation) page.
More information about SUMO Traffic Genetator can be found in [SUMO's website](https://www.dlr.de/ts/en/desktopdefault.aspx/tabid-9883/16931_read-41000/).
