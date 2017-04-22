JSON files listing node ids of SAFE network. Node ids are grouped by sections and files are grouped by day (one directory per day).

Each file represents a snapshot at a point in time. They were generated approximatively every minute. They contain the following attributes:

- complete: Indicate if all the sections of network were returned

- min_section_size_ok: Indicate if all sections have at least 8 nodes

- id: Node id of the vault requesting the routing tables of sections in the network

- total_count: Real total number of nodes in the network

- debug_estimate_count: Concatenation of complete attribute, debug_estimate_count attribute, total_count attribute and estimated number of nodes (as returned by network_size_estimate() routing table function)

- initial: Sections in routing table of requester vault

- requested: Requested sections

- seconds: Elapsed time before receiving all sections

- prefixes: Array of received sections. Each element has following attributes:

    - prefix: Section prefix

    - type: Indicates content origin:
    
        - "Ours": Content is from our own section
        
        - "Neighbour": Content is from our routing table

        - "Requested": Content was returned as part of a request

    - count: number of nodes in this section

    - ids: Node ids in the section