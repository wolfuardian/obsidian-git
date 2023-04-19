Open5GCore Rel. 7 implements the essential features necessary for the end-to-end 5G system deployment and aligned with 3GPP Release 15 and 16. Open5GCore Rel. 7 includes a set of new components addressing 5G Standalone Core Network which were developed separately from the previous EPC components. Through this, a genuine 5G core network can be used as parts of the testbeds.
![[Pasted image 20230419155642.png]]
Open5GCore implements the features necessary for the end-to-end 5G system trials and validation:

-   Implementation of 5G core network: AMF, SMF, AUSF, UDM, NRF, UPF
-   Integration with the 5G NR using the 5G interfaces [N1, N2, N3], 5G NAS and NG-AP
-   Implementing control-user plane split with PFCP [N4]
-   SBA Control Plane [HTTP/2, OpenAPI, REST]
-   Interoperating with many 5G NR SA base stations and UEs
-   Interoperating with external NFs/AFs over HTTP/2 or HTTP1.1

All main procedures are supported:

-   Registration, Deregistration, PDU Session Establishment
-   Service Activation & Deactivation, Paging, Mobility Update
-   N2 handovers

Testing (no radio) includes 5G UE and gNB SA Simulation.