
# SONiC 201904 Release Notes  

# Branch Location  
https://github.com/Azure/sonic-buildimage/tree/201904

# Dependency Version

- Linux kernel version - 4.9.110-3+deb9u6  - Linux 4.9 for 64-bit PCs
- SAI version - SAI 1.4 
- FRR - 6.0.2-0 
- LLDPD - 0.9.6-` 
- TeamD - 1.26-1 
- SNMPD - 5.7.3+dfsg-1.5 
- Python - 2.7.13, python3 - 3.5.3
- syncd - 1.0.0, swss - 1.0.0
- radvd - 1:2.17-2~bpo9+1
- isc-dhcp-relay - 4.3.5-3.1
- sonic-telemetry - 0.1
- redis-server, redis-tools - 3:3.2.4-1~bpo8+1


# Feature List 

| # | Big Feature List and Design Doc Link   | Comments |
|---:     |---       |---       |
| 1       | [FRR as default routing stack](http://docs.frrouting.org/en/latest/) |  |
| 2       | Upgrade each docker to stretch version | SNMPD, LLDPD, Teamd |
| 3       | Upgrade docker engine to 18.09 |  |
| 4       | [Everflow enhancement](https://github.com/Azure/SONiC/blob/bb4f4a3a85935a38ec7f9625ef62cbe58c0998b4/doc/SONiC_EVERFLOW_IPv6.pdf) |  |
| 5       | [Egress ACL bug fix and ACL CLI enhancement](https://github.com/Azure/SONiC/blob/dfa7e58292deb4d7b10d1e0ca73f296cd206e9d2/doc/acl/egress-acl-bug-fix-description.md)  |  |
| 6       | [L3 RIF counter support](https://github.com/Azure/SONiC/blob/master/doc/RIF_counters.md) [PR](https://github.com/Azure/SONiC/pull/310)  |  |
| 7       | [PMon Refactoring](https://github.com/Azure/SONiC/tree/master/doc/pmon)  |  |
| 8       | BGP-EVPN support (type 5) (related HLD [Fpmsyncd](https://github.com/Azure/SONiC/pull/375), [vxlanmgr](https://github.com/Azure/SONiC/pull/369), [template](https://github.com/Azure/sonic-buildimage/pull/2838/files) ) |  |


# Security Updates  
1. Kernel upgrade from 4.9.110-3+deb9u2 to 4.9.110-3+deb9u6
   Change log: https://tracker.debian.org/media/packages/l/linux/changelog-4.9.110-3deb9u6

2. Docker upgrade from 18.09.0\~3 to 18.09.2\~3 to address below issue:  
   https://security-tracker.debian.org/tracker/CVE-2019-5736


	# SAI APIs used in this release  

| SAI APIs used in this 201904 release 
|---
| SAI_ACL_ACTION_TYPE_ACL_DTEL_FLOW_OP
| SAI_ACL_ACTION_TYPE_DTEL_DROP_REPORT_ENABLE
| SAI_ACL_ACTION_TYPE_DTEL_FLOW_SAMPLE_PERCENT
| SAI_ACL_ACTION_TYPE_DTEL_INT_SESSION
| SAI_ACL_ACTION_TYPE_DTEL_REPORT_ALL_PACKETS
| SAI_ACL_ACTION_TYPE_DTEL_TAIL_DROP_REPORT_ENABLE
| SAI_ACL_BIND_POINT_TYPE_LAG
| SAI_ACL_BIND_POINT_TYPE_PORT
| SAI_ACL_BIND_POINT_TYPE_ROUTER_INTERFACE
| SAI_ACL_BIND_POINT_TYPE_SWITCH
| SAI_ACL_BIND_POINT_TYPE_VLAN
| SAI_ACL_COUNTER_ATTR_BYTES
| SAI_ACL_COUNTER_ATTR_ENABLE_BYTE_COUNT
| SAI_ACL_COUNTER_ATTR_ENABLE_PACKET_COUNT
| SAI_ACL_COUNTER_ATTR_PACKETS
| SAI_ACL_COUNTER_ATTR_TABLE_ID
| SAI_ACL_DTEL_FLOW_OP_INT
| SAI_ACL_DTEL_FLOW_OP_IOAM
| SAI_ACL_DTEL_FLOW_OP_NOP
| SAI_ACL_DTEL_FLOW_OP_POSTCARD
| SAI_ACL_ENTRY_ATTR_ACTION_ACL_DTEL_FLOW_OP
| SAI_ACL_ENTRY_ATTR_ACTION_COUNTER
| SAI_ACL_ENTRY_ATTR_ACTION_DTEL_DROP_REPORT_ENABLE
| SAI_ACL_ENTRY_ATTR_ACTION_DTEL_FLOW_SAMPLE_PERCENT
| SAI_ACL_ENTRY_ATTR_ACTION_DTEL_INT_SESSION
| SAI_ACL_ENTRY_ATTR_ACTION_DTEL_REPORT_ALL_PACKETS
| SAI_ACL_ENTRY_ATTR_ACTION_DTEL_TAIL_DROP_REPORT_ENABLE
| SAI_ACL_ENTRY_ATTR_ACTION_MIRROR_INGRESS
| SAI_ACL_ENTRY_ATTR_ACTION_PACKET_ACTION
| SAI_ACL_ENTRY_ATTR_ACTION_REDIRECT
| SAI_ACL_ENTRY_ATTR_ACTION_SET_PACKET_COLOR
| SAI_ACL_ENTRY_ATTR_ADMIN_STATE
| SAI_ACL_ENTRY_ATTR_FIELD_ACL_IP_TYPE
| SAI_ACL_ENTRY_ATTR_FIELD_ACL_RANGE_TYPE
| SAI_ACL_ENTRY_ATTR_FIELD_DSCP
| SAI_ACL_ENTRY_ATTR_FIELD_DST_IP
| SAI_ACL_ENTRY_ATTR_FIELD_DST_IPV6
| SAI_ACL_ENTRY_ATTR_FIELD_ETHER_TYPE
| SAI_ACL_ENTRY_ATTR_FIELD_INNER_ETHER_TYPE
| SAI_ACL_ENTRY_ATTR_FIELD_INNER_IP_PROTOCOL
| SAI_ACL_ENTRY_ATTR_FIELD_INNER_L4_DST_PORT
| SAI_ACL_ENTRY_ATTR_FIELD_INNER_L4_SRC_PORT
| SAI_ACL_ENTRY_ATTR_FIELD_IN_PORTS
| SAI_ACL_ENTRY_ATTR_FIELD_IP_PROTOCOL
| SAI_ACL_ENTRY_ATTR_FIELD_L4_DST_PORT
| SAI_ACL_ENTRY_ATTR_FIELD_L4_SRC_PORT
| SAI_ACL_ENTRY_ATTR_FIELD_OUT_PORTS
| SAI_ACL_ENTRY_ATTR_FIELD_SRC_IP
| SAI_ACL_ENTRY_ATTR_FIELD_SRC_IPV6
| SAI_ACL_ENTRY_ATTR_FIELD_TC
| SAI_ACL_ENTRY_ATTR_FIELD_TCP_FLAGS
| SAI_ACL_ENTRY_ATTR_FIELD_TUNNEL_VNI
| SAI_ACL_ENTRY_ATTR_PRIORITY
| SAI_ACL_ENTRY_ATTR_TABLE_ID
| SAI_ACL_IP_TYPE_ANY
| SAI_ACL_IP_TYPE_ARP
| SAI_ACL_IP_TYPE_ARP_REPLY
| SAI_ACL_IP_TYPE_ARP_REQUEST
| SAI_ACL_IP_TYPE_IP
| SAI_ACL_IP_TYPE_IPV4ANY
| SAI_ACL_IP_TYPE_IPV6ANY
| SAI_ACL_IP_TYPE_NON_IP
| SAI_ACL_IP_TYPE_NON_IPV4
| SAI_ACL_IP_TYPE_NON_IPV6
| SAI_ACL_RANGE_ATTR_LIMIT
| SAI_ACL_RANGE_ATTR_TYPE
| SAI_ACL_RANGE_TYPE_L4_DST_PORT_RANGE
| SAI_ACL_RANGE_TYPE_L4_SRC_PORT_RANGE
| SAI_ACL_STAGE_EGRESS
| SAI_ACL_STAGE_INGRESS
| SAI_ACL_TABLE_ATTR_ACL_ACTION_TYPE_LIST
| SAI_ACL_TABLE_ATTR_ACL_BIND_POINT_TYPE_LIST
| SAI_ACL_TABLE_ATTR_ACL_STAGE
| SAI_ACL_TABLE_ATTR_AVAILABLE_ACL_COUNTER
| SAI_ACL_TABLE_ATTR_AVAILABLE_ACL_ENTRY
| SAI_ACL_TABLE_ATTR_FIELD_ACL_IP_TYPE
| SAI_ACL_TABLE_ATTR_FIELD_ACL_RANGE_TYPE
| SAI_ACL_TABLE_ATTR_FIELD_DSCP
| SAI_ACL_TABLE_ATTR_FIELD_DST_IP
| SAI_ACL_TABLE_ATTR_FIELD_DST_IPV6
| SAI_ACL_TABLE_ATTR_FIELD_ECN
| SAI_ACL_TABLE_ATTR_FIELD_ETHER_TYPE
| SAI_ACL_TABLE_ATTR_FIELD_INNER_DST_IP
| SAI_ACL_TABLE_ATTR_FIELD_INNER_ETHER_TYPE
| SAI_ACL_TABLE_ATTR_FIELD_INNER_SRC_IP
| SAI_ACL_TABLE_ATTR_FIELD_IP_PROTOCOL
| SAI_ACL_TABLE_ATTR_FIELD_L4_DST_PORT
| SAI_ACL_TABLE_ATTR_FIELD_L4_SRC_PORT
| SAI_ACL_TABLE_ATTR_FIELD_SRC_IP
| SAI_ACL_TABLE_ATTR_FIELD_SRC_IPV6
| SAI_ACL_TABLE_ATTR_FIELD_TC
| SAI_ACL_TABLE_ATTR_FIELD_TCP_FLAGS
| SAI_ACL_TABLE_ATTR_FIELD_TUNNEL_VNI
| SAI_ACL_TABLE_GROUP_ATTR_ACL_BIND_POINT_TYPE_LIST
| SAI_ACL_TABLE_GROUP_ATTR_ACL_STAGE
| SAI_ACL_TABLE_GROUP_ATTR_TYPE
| SAI_ACL_TABLE_GROUP_MEMBER_ATTR_ACL_TABLE_GROUP_ID
| SAI_ACL_TABLE_GROUP_MEMBER_ATTR_ACL_TABLE_ID
| SAI_ACL_TABLE_GROUP_MEMBER_ATTR_PRIORITY
| SAI_ACL_TABLE_GROUP_TYPE_PARALLEL
| SAI_API_ACL
| SAI_API_BMTOR
| SAI_API_BRIDGE
| SAI_API_BUFFER
| SAI_API_DTEL
| SAI_API_FDB
| SAI_API_HOSTIF
| SAI_API_LAG
| SAI_API_MIRROR
| SAI_API_NEIGHBOR
| SAI_API_NEXT_HOP
| SAI_API_NEXT_HOP_GROUP
| SAI_API_POLICER
| SAI_API_PORT
| SAI_API_QOS_MAP
| SAI_API_QUEUE
| SAI_API_ROUTE
| SAI_API_ROUTER_INTERFACE
| SAI_API_SCHEDULER
| SAI_API_SCHEDULER_GROUP
| SAI_API_SWITCH
| SAI_API_TUNNEL
| SAI_API_VIRTUAL_ROUTER
| SAI_API_VLAN
| SAI_API_WRED
| SAI_BRIDGE_ATTR_PORT_LIST
| SAI_BRIDGE_ATTR_TYPE
| SAI_BRIDGE_PORT_ATTR_ADMIN_STATE
| SAI_BRIDGE_PORT_ATTR_BRIDGE_ID
| SAI_BRIDGE_PORT_ATTR_FDB_LEARNING_MODE
| SAI_BRIDGE_PORT_ATTR_PORT_ID
| SAI_BRIDGE_PORT_ATTR_RIF_ID
| SAI_BRIDGE_PORT_ATTR_TUNNEL_ID
| SAI_BRIDGE_PORT_ATTR_TYPE
| SAI_BRIDGE_PORT_FDB_LEARNING_MODE_DISABLE
| SAI_BRIDGE_PORT_FDB_LEARNING_MODE_HW
| SAI_BRIDGE_PORT_TYPE_1D_ROUTER
| SAI_BRIDGE_PORT_TYPE_1Q_ROUTER
| SAI_BRIDGE_PORT_TYPE_PORT
| SAI_BRIDGE_PORT_TYPE_TUNNEL
| SAI_BRIDGE_TYPE_1D
| SAI_BUFFER_POOL_ATTR_SIZE
| SAI_BUFFER_POOL_ATTR_THRESHOLD_MODE
| SAI_BUFFER_POOL_ATTR_TYPE
| SAI_BUFFER_POOL_ATTR_XOFF_SIZE
| SAI_BUFFER_POOL_THRESHOLD_MODE_DYNAMIC
| SAI_BUFFER_POOL_THRESHOLD_MODE_STATIC
| SAI_BUFFER_POOL_TYPE_EGRESS
| SAI_BUFFER_POOL_TYPE_INGRESS
| SAI_BUFFER_PROFILE_ATTR_BUFFER_SIZE
| SAI_BUFFER_PROFILE_ATTR_POOL_ID
| SAI_BUFFER_PROFILE_ATTR_SHARED_DYNAMIC_TH
| SAI_BUFFER_PROFILE_ATTR_SHARED_STATIC_TH
| SAI_BUFFER_PROFILE_ATTR_THRESHOLD_MODE
| SAI_BUFFER_PROFILE_ATTR_XOFF_TH
| SAI_BUFFER_PROFILE_ATTR_XON_OFFSET_TH
| SAI_BUFFER_PROFILE_ATTR_XON_TH
| SAI_BUFFER_PROFILE_THRESHOLD_MODE_DYNAMIC
| SAI_BUFFER_PROFILE_THRESHOLD_MODE_STATIC
| SAI_DTEL_ATTR_DROP_REPORT_ENABLE
| SAI_DTEL_ATTR_FLOW_STATE_CLEAR_CYCLE
| SAI_DTEL_ATTR_INT_ENDPOINT_ENABLE
| SAI_DTEL_ATTR_INT_L4_DSCP
| SAI_DTEL_ATTR_INT_TRANSIT_ENABLE
| SAI_DTEL_ATTR_LATENCY_SENSITIVITY
| SAI_DTEL_ATTR_POSTCARD_ENABLE
| SAI_DTEL_ATTR_QUEUE_REPORT_ENABLE
| SAI_DTEL_ATTR_SINK_PORT_LIST
| SAI_DTEL_ATTR_SWITCH_ID
| SAI_DTEL_EVENT_ATTR_DSCP_VALUE
| SAI_DTEL_EVENT_ATTR_REPORT_SESSION
| SAI_DTEL_EVENT_ATTR_TYPE
| SAI_DTEL_EVENT_TYPE_DROP_REPORT
| SAI_DTEL_EVENT_TYPE_FLOW_REPORT_ALL_PACKETS
| SAI_DTEL_EVENT_TYPE_FLOW_STATE
| SAI_DTEL_EVENT_TYPE_FLOW_TCPFLAG
| SAI_DTEL_EVENT_TYPE_QUEUE_REPORT_TAIL_DROP
| SAI_DTEL_EVENT_TYPE_QUEUE_REPORT_THRESHOLD_BREACH
| SAI_DTEL_INT_SESSION_ATTR_COLLECT_EGRESS_TIMESTAMP
| SAI_DTEL_INT_SESSION_ATTR_COLLECT_INGRESS_TIMESTAMP
| SAI_DTEL_INT_SESSION_ATTR_COLLECT_QUEUE_INFO
| SAI_DTEL_INT_SESSION_ATTR_COLLECT_SWITCH_ID
| SAI_DTEL_INT_SESSION_ATTR_COLLECT_SWITCH_PORTS
| SAI_DTEL_INT_SESSION_ATTR_MAX_HOP_COUNT
| SAI_DTEL_QUEUE_REPORT_ATTR_BREACH_QUOTA
| SAI_DTEL_QUEUE_REPORT_ATTR_DEPTH_THRESHOLD
| SAI_DTEL_QUEUE_REPORT_ATTR_LATENCY_THRESHOLD
| SAI_DTEL_QUEUE_REPORT_ATTR_QUEUE_ID
| SAI_DTEL_QUEUE_REPORT_ATTR_TAIL_DROP
| SAI_DTEL_REPORT_SESSION_ATTR_DST_IP_LIST
| SAI_DTEL_REPORT_SESSION_ATTR_SRC_IP
| SAI_DTEL_REPORT_SESSION_ATTR_TRUNCATE_SIZE
| SAI_DTEL_REPORT_SESSION_ATTR_UDP_DST_PORT
| SAI_DTEL_REPORT_SESSION_ATTR_VIRTUAL_ROUTER_ID
| SAI_ECN_MARK_MODE_ALL
| SAI_ECN_MARK_MODE_GREEN
| SAI_ECN_MARK_MODE_GREEN_RED
| SAI_ECN_MARK_MODE_GREEN_YELLOW
| SAI_ECN_MARK_MODE_NONE
| SAI_ECN_MARK_MODE_RED
| SAI_ECN_MARK_MODE_YELLOW
| SAI_ECN_MARK_MODE_YELLOW_RED
| SAI_ERSPAN_ENCAPSULATION_TYPE_MIRROR_L3_GRE_TUNNEL
| SAI_FDB_ENTRY_ATTR_BRIDGE_PORT_ID
| SAI_FDB_ENTRY_ATTR_ENDPOINT_IP
| SAI_FDB_ENTRY_ATTR_PACKET_ACTION
| SAI_FDB_ENTRY_ATTR_TYPE
| SAI_FDB_ENTRY_TYPE_DYNAMIC
| SAI_FDB_ENTRY_TYPE_STATIC
| SAI_FDB_EVENT_AGED
| SAI_FDB_EVENT_FLUSHED
| SAI_FDB_EVENT_LEARNED
| SAI_FDB_EVENT_MOVE
| SAI_HOSTIF_ATTR_NAME
| SAI_HOSTIF_ATTR_OBJ_ID
| SAI_HOSTIF_ATTR_OPER_STATUS
| SAI_HOSTIF_ATTR_TYPE
| SAI_HOSTIF_ATTR_VLAN_TAG
| SAI_HOSTIF_NAME_SIZE
| SAI_HOSTIF_TABLE_ENTRY_ATTR_CHANNEL_TYPE
| SAI_HOSTIF_TABLE_ENTRY_ATTR_TYPE
| SAI_HOSTIF_TABLE_ENTRY_CHANNEL_TYPE_NETDEV_PHYSICAL_PORT
| SAI_HOSTIF_TABLE_ENTRY_TYPE_WILDCARD
| SAI_HOSTIF_TRAP_ATTR_PACKET_ACTION
| SAI_HOSTIF_TRAP_ATTR_TRAP_GROUP
| SAI_HOSTIF_TRAP_ATTR_TRAP_PRIORITY
| SAI_HOSTIF_TRAP_ATTR_TRAP_TYPE
| SAI_HOSTIF_TRAP_GROUP_ATTR_POLICER
| SAI_HOSTIF_TRAP_GROUP_ATTR_QUEUE
| SAI_HOSTIF_TRAP_TYPE_ARP_REQUEST
| SAI_HOSTIF_TRAP_TYPE_ARP_RESPONSE
| SAI_HOSTIF_TRAP_TYPE_BGP
| SAI_HOSTIF_TRAP_TYPE_BGPV6
| SAI_HOSTIF_TRAP_TYPE_DHCP
| SAI_HOSTIF_TRAP_TYPE_DHCPV6
| SAI_HOSTIF_TRAP_TYPE_EAPOL
| SAI_HOSTIF_TRAP_TYPE_IGMP_TYPE_LEAVE
| SAI_HOSTIF_TRAP_TYPE_IGMP_TYPE_QUERY
| SAI_HOSTIF_TRAP_TYPE_IGMP_TYPE_V1_REPORT
| SAI_HOSTIF_TRAP_TYPE_IGMP_TYPE_V2_REPORT
| SAI_HOSTIF_TRAP_TYPE_IGMP_TYPE_V3_REPORT
| SAI_HOSTIF_TRAP_TYPE_IP2ME
| SAI_HOSTIF_TRAP_TYPE_IPV6_MLD_V1_DONE
| SAI_HOSTIF_TRAP_TYPE_IPV6_MLD_V1_REPORT
| SAI_HOSTIF_TRAP_TYPE_IPV6_MLD_V1_V2
| SAI_HOSTIF_TRAP_TYPE_IPV6_NEIGHBOR_DISCOVERY
| SAI_HOSTIF_TRAP_TYPE_L3_MTU_ERROR
| SAI_HOSTIF_TRAP_TYPE_LACP
| SAI_HOSTIF_TRAP_TYPE_LLDP
| SAI_HOSTIF_TRAP_TYPE_MLD_V2_REPORT
| SAI_HOSTIF_TRAP_TYPE_OSPF
| SAI_HOSTIF_TRAP_TYPE_OSPFV6
| SAI_HOSTIF_TRAP_TYPE_PIM
| SAI_HOSTIF_TRAP_TYPE_PVRST
| SAI_HOSTIF_TRAP_TYPE_ROUTER_CUSTOM_RANGE_BASE
| SAI_HOSTIF_TRAP_TYPE_SAMPLEPACKET
| SAI_HOSTIF_TRAP_TYPE_SNMP
| SAI_HOSTIF_TRAP_TYPE_SSH
| SAI_HOSTIF_TRAP_TYPE_STP
| SAI_HOSTIF_TRAP_TYPE_SWITCH_CUSTOM_RANGE_BASE
| SAI_HOSTIF_TRAP_TYPE_TTL_ERROR
| SAI_HOSTIF_TRAP_TYPE_UDLD
| SAI_HOSTIF_TRAP_TYPE_VRRP
| SAI_HOSTIF_TRAP_TYPE_VRRPV6
| SAI_HOSTIF_TYPE_NETDEV
| SAI_HOSTIF_VLAN_TAG_KEEP
| SAI_HOSTIF_VLAN_TAG_ORIGINAL
| SAI_HOSTIF_VLAN_TAG_STRIP
| SAI_INGRESS_PRIORITY_GROUP_ATTR_BUFFER_PROFILE
| SAI_INGRESS_PRIORITY_GROUP_STAT_DROPPED_PACKETS
| SAI_INGRESS_PRIORITY_GROUP_STAT_PACKETS
| SAI_INGRESS_PRIORITY_GROUP_STAT_SHARED_WATERMARK_BYTES
| SAI_INGRESS_PRIORITY_GROUP_STAT_XOFF_ROOM_WATERMARK_BYTES
| SAI_IP_ADDR_FAMILY_IPV4
| SAI_IP_ADDR_FAMILY_IPV6
| SAI_LAG_ATTR_EGRESS_ACL
| SAI_LAG_ATTR_INGRESS_ACL
| SAI_LAG_ATTR_PORT_VLAN_ID
| SAI_LAG_MEMBER_ATTR_LAG_ID
| SAI_LAG_MEMBER_ATTR_PORT_ID
| SAI_LOG_LEVEL_NOTICE
| SAI_METER_TYPE_BYTES
| SAI_METER_TYPE_PACKETS
| SAI_MIRROR_SESSION_ATTR_DST_IP_ADDRESS
| SAI_MIRROR_SESSION_ATTR_DST_MAC_ADDRESS
| SAI_MIRROR_SESSION_ATTR_ERSPAN_ENCAPSULATION_TYPE
| SAI_MIRROR_SESSION_ATTR_GRE_PROTOCOL_TYPE
| SAI_MIRROR_SESSION_ATTR_IPHDR_VERSION
| SAI_MIRROR_SESSION_ATTR_MONITOR_PORT
| SAI_MIRROR_SESSION_ATTR_SRC_IP_ADDRESS
| SAI_MIRROR_SESSION_ATTR_SRC_MAC_ADDRESS
| SAI_MIRROR_SESSION_ATTR_TC
| SAI_MIRROR_SESSION_ATTR_TOS
| SAI_MIRROR_SESSION_ATTR_TTL
| SAI_MIRROR_SESSION_ATTR_TYPE
| SAI_MIRROR_SESSION_ATTR_VLAN_CFI
| SAI_MIRROR_SESSION_ATTR_VLAN_HEADER_VALID
| SAI_MIRROR_SESSION_ATTR_VLAN_ID
| SAI_MIRROR_SESSION_ATTR_VLAN_PRI
| SAI_MIRROR_SESSION_ATTR_VLAN_TPID
| SAI_MIRROR_SESSION_TYPE_ENHANCED_REMOTE
| SAI_NEIGHBOR_ENTRY_ATTR_DST_MAC_ADDRESS
| SAI_NEXT_HOP_ATTR_IP
| SAI_NEXT_HOP_ATTR_ROUTER_INTERFACE_ID
| SAI_NEXT_HOP_ATTR_TUNNEL_ID
| SAI_NEXT_HOP_ATTR_TUNNEL_MAC
| SAI_NEXT_HOP_ATTR_TUNNEL_VNI
| SAI_NEXT_HOP_ATTR_TYPE
| SAI_NEXT_HOP_GROUP_ATTR_TYPE
| SAI_NEXT_HOP_GROUP_MEMBER_ATTR_NEXT_HOP_GROUP_ID
| SAI_NEXT_HOP_GROUP_MEMBER_ATTR_NEXT_HOP_ID
| SAI_NEXT_HOP_GROUP_TYPE_ECMP
| SAI_NEXT_HOP_TYPE_IP
| SAI_NEXT_HOP_TYPE_TUNNEL_ENCAP
| SAI_NULL_OBJECT_ID
| SAI_OBJECT_TYPE
| SAI_OBJECT_TYPE_ACL_ENTRY
| SAI_OBJECT_TYPE_ACL_RANGE
| SAI_OBJECT_TYPE_ACL_TABLE
| SAI_OBJECT_TYPE_ACL_TABLE_GROUP
| SAI_OBJECT_TYPE_ACL_TABLE_GROUP_MEMBER
| SAI_OBJECT_TYPE_BRIDGE_PORT
| SAI_OBJECT_TYPE_BUFFER_PROFILE
| SAI_OBJECT_TYPE_DTEL
| SAI_OBJECT_TYPE_DTEL_EVENT
| SAI_OBJECT_TYPE_DTEL_INT_SESSION
| SAI_OBJECT_TYPE_DTEL_QUEUE_REPORT
| SAI_OBJECT_TYPE_DTEL_REPORT_SESSION
| SAI_OBJECT_TYPE_FDB_ENTRY
| SAI_OBJECT_TYPE_HOSTIF
| SAI_OBJECT_TYPE_INGRESS_PRIORITY_GROUP
| SAI_OBJECT_TYPE_LAG
| SAI_OBJECT_TYPE_LAG_MEMBER
| SAI_OBJECT_TYPE_MIRROR_SESSION
| SAI_OBJECT_TYPE_NEIGHBOR_ENTRY
| SAI_OBJECT_TYPE_NEXT_HOP
| SAI_OBJECT_TYPE_NEXT_HOP_GROUP
| SAI_OBJECT_TYPE_NEXT_HOP_GROUP_MEMBER
| SAI_OBJECT_TYPE_NULL
| SAI_OBJECT_TYPE_PORT
| SAI_OBJECT_TYPE_QUEUE
| SAI_OBJECT_TYPE_ROUTE_ENTRY
| SAI_OBJECT_TYPE_ROUTER_INTERFACE
| SAI_OBJECT_TYPE_SWITCH
| SAI_OBJECT_TYPE_TABLE_BITMAP_CLASSIFICATION_ENTRY
| SAI_OBJECT_TYPE_TABLE_BITMAP_ROUTER_ENTRY
| SAI_OBJECT_TYPE_TUNNEL
| SAI_OBJECT_TYPE_TUNNEL_MAP
| SAI_OBJECT_TYPE_TUNNEL_MAP_ENTRY
| SAI_OBJECT_TYPE_TUNNEL_TERM_TABLE_ENTRY
| SAI_OBJECT_TYPE_VIRTUAL_ROUTER
| SAI_OBJECT_TYPE_VLAN
| SAI_OBJECT_TYPE_VLAN_MEMBER
| SAI_PACKET_ACTION_COPY
| SAI_PACKET_ACTION_COPY_CANCEL
| SAI_PACKET_ACTION_DENY
| SAI_PACKET_ACTION_DROP
| SAI_PACKET_ACTION_FORWARD
| SAI_PACKET_ACTION_LOG
| SAI_PACKET_ACTION_TRANSIT
| SAI_PACKET_ACTION_TRAP
| SAI_PACKET_COLOR_YELLOW
| SAI_POLICER_ATTR_CBS
| SAI_POLICER_ATTR_CIR
| SAI_POLICER_ATTR_COLOR_SOURCE
| SAI_POLICER_ATTR_GREEN_PACKET_ACTION
| SAI_POLICER_ATTR_METER_TYPE
| SAI_POLICER_ATTR_MODE
| SAI_POLICER_ATTR_PBS
| SAI_POLICER_ATTR_PIR
| SAI_POLICER_ATTR_RED_PACKET_ACTION
| SAI_POLICER_ATTR_YELLOW_PACKET_ACTION
| SAI_POLICER_COLOR_SOURCE_AWARE
| SAI_POLICER_COLOR_SOURCE_BLIND
| SAI_POLICER_MODE_SR_TCM
| SAI_POLICER_MODE_STORM_CONTROL
| SAI_POLICER_MODE_TR_TCM
| SAI_PORT_ATTR_ADMIN_STATE
| SAI_PORT_ATTR_ADVERTISED_SPEED
| SAI_PORT_ATTR_AUTO_NEG_MODE
| SAI_PORT_ATTR_EGRESS_ACL
| SAI_PORT_ATTR_FEC_MODE
| SAI_PORT_ATTR_HW_LANE_LIST
| SAI_PORT_ATTR_INGRESS_ACL
| SAI_PORT_ATTR_INGRESS_PRIORITY_GROUP_LIST
| SAI_PORT_ATTR_MTU
| SAI_PORT_ATTR_NUMBER_OF_INGRESS_PRIORITY_GROUPS
| SAI_PORT_ATTR_OPER_STATUS
| SAI_PORT_ATTR_PORT_VLAN_ID
| SAI_PORT_ATTR_PRIORITY_FLOW_CONTROL
| SAI_PORT_ATTR_PRIORITY_FLOW_CONTROL_MODE
| SAI_PORT_ATTR_PRIORITY_FLOW_CONTROL_RX
| SAI_PORT_ATTR_PRIORITY_FLOW_CONTROL_TX
| SAI_PORT_ATTR_QOS_DSCP_TO_TC_MAP
| SAI_PORT_ATTR_QOS_EGRESS_BUFFER_PROFILE_LIST
| SAI_PORT_ATTR_QOS_INGRESS_BUFFER_PROFILE_LIST
| SAI_PORT_ATTR_QOS_NUMBER_OF_QUEUES
| SAI_PORT_ATTR_QOS_NUMBER_OF_SCHEDULER_GROUPS
| SAI_PORT_ATTR_QOS_PFC_PRIORITY_TO_PRIORITY_GROUP_MAP
| SAI_PORT_ATTR_QOS_PFC_PRIORITY_TO_QUEUE_MAP
| SAI_PORT_ATTR_QOS_QUEUE_LIST
| SAI_PORT_ATTR_QOS_SCHEDULER_GROUP_LIST
| SAI_PORT_ATTR_QOS_TC_TO_PRIORITY_GROUP_MAP
| SAI_PORT_ATTR_QOS_TC_TO_QUEUE_MAP
| SAI_PORT_ATTR_SPEED
| SAI_PORT_ATTR_SUPPORTED_SPEED
| SAI_PORT_FEC_MODE_FC
| SAI_PORT_FEC_MODE_NONE
| SAI_PORT_FEC_MODE_RS
| SAI_PORT_OPER_STATUS_DOWN
| SAI_PORT_OPER_STATUS_NOT_PRESENT
| SAI_PORT_OPER_STATUS_TESTING
| SAI_PORT_OPER_STATUS_UNKNOWN
| SAI_PORT_OPER_STATUS_UP
| SAI_PORT_PRIORITY_FLOW_CONTROL_MODE_COMBINED
| SAI_PORT_PRIORITY_FLOW_CONTROL_MODE_SEPARATE
| SAI_PORT_STAT_ETHER_IN_PKTS_128_TO_255_OCTETS
| SAI_PORT_STAT_ETHER_RX_OVERSIZE_PKTS
| SAI_PORT_STAT_ETHER_STATS_TX_NO_ERRORS
| SAI_PORT_STAT_ETHER_TX_OVERSIZE_PKTS
| SAI_PORT_STAT_IF_IN_BROADCAST_PKTS
| SAI_PORT_STAT_IF_IN_DISCARDS
| SAI_PORT_STAT_IF_IN_ERRORS
| SAI_PORT_STAT_IF_IN_MULTICAST_PKTS
| SAI_PORT_STAT_IF_IN_NON_UCAST_PKTS
| SAI_PORT_STAT_IF_IN_OCTETS
| SAI_PORT_STAT_IF_IN_UCAST_PKTS
| SAI_PORT_STAT_IF_IN_UNKNOWN_PROTOS
| SAI_PORT_STAT_IF_OUT_BROADCAST_PKTS
| SAI_PORT_STAT_IF_OUT_DISCARDS
| SAI_PORT_STAT_IF_OUT_ERRORS
| SAI_PORT_STAT_IF_OUT_MULTICAST_PKTS
| SAI_PORT_STAT_IF_OUT_NON_UCAST_PKTS
| SAI_PORT_STAT_IF_OUT_OCTETS
| SAI_PORT_STAT_IF_OUT_QLEN
| SAI_PORT_STAT_IF_OUT_UCAST_PKTS
| SAI_PORT_STAT_IP_IN_UCAST_PKTS
| SAI_PORT_STAT_PAUSE_RX_PKTS
| SAI_PORT_STAT_PAUSE_TX_PKTS
| SAI_PORT_STAT_PFC_
| SAI_PORT_STAT_PFC_0_ON2OFF_RX_PKTS
| SAI_PORT_STAT_PFC_0_RX_PAUSE_DURATION
| SAI_PORT_STAT_PFC_0_RX_PKTS
| SAI_PORT_STAT_PFC_0_TX_PKTS
| SAI_PORT_STAT_PFC_1_ON2OFF_RX_PKTS
| SAI_PORT_STAT_PFC_1_RX_PAUSE_DURATION
| SAI_PORT_STAT_PFC_1_RX_PKTS
| SAI_PORT_STAT_PFC_1_TX_PKTS
| SAI_PORT_STAT_PFC_2_ON2OFF_RX_PKTS
| SAI_PORT_STAT_PFC_2_RX_PAUSE_DURATION
| SAI_PORT_STAT_PFC_2_RX_PKTS
| SAI_PORT_STAT_PFC_2_TX_PKTS
| SAI_PORT_STAT_PFC_3_ON2OFF_RX_PKTS
| SAI_PORT_STAT_PFC_3_RX_PAUSE_DURATION
| SAI_PORT_STAT_PFC_3_RX_PKTS
| SAI_PORT_STAT_PFC_3_TX_PKTS
| SAI_PORT_STAT_PFC_4_ON2OFF_RX_PKTS
| SAI_PORT_STAT_PFC_4_RX_PAUSE_DURATION
| SAI_PORT_STAT_PFC_4_RX_PKTS
| SAI_PORT_STAT_PFC_4_TX_PKTS
| SAI_PORT_STAT_PFC_5_ON2OFF_RX_PKTS
| SAI_PORT_STAT_PFC_5_RX_PAUSE_DURATION
| SAI_PORT_STAT_PFC_5_RX_PKTS
| SAI_PORT_STAT_PFC_5_TX_PKTS
| SAI_PORT_STAT_PFC_6_ON2OFF_RX_PKTS
| SAI_PORT_STAT_PFC_6_RX_PAUSE_DURATION
| SAI_PORT_STAT_PFC_6_RX_PKTS
| SAI_PORT_STAT_PFC_6_TX_PKTS
| SAI_PORT_STAT_PFC_7_ON2OFF_RX_PKTS
| SAI_PORT_STAT_PFC_7_RX_PAUSE_DURATION
| SAI_PORT_STAT_PFC_7_RX_PKTS
| SAI_PORT_STAT_PFC_7_TX_PKTS
| SAI_PORT_STAT_PFC_PREFIX
| SAI_QOS_MAP_ATTR_MAP_TO_VALUE_LIST
| SAI_QOS_MAP_ATTR_TYPE
| SAI_QOS_MAP_DSCP_TO_TC
| SAI_QOS_MAP_TC_TO_QUEUE
| SAI_QOS_MAP_TYPE_DSCP_TO_TC
| SAI_QOS_MAP_TYPE_PFC_PRIORITY_TO_PRIORITY_GROUP
| SAI_QOS_MAP_TYPE_PFC_PRIORITY_TO_QUEUE
| SAI_QOS_MAP_TYPE_TC_TO_PRIORITY_GROUP
| SAI_QOS_MAP_TYPE_TC_TO_QUEUE
| SAI_QUEUE_ATTR_BUFFER_PROFILE_ID
| SAI_QUEUE_ATTR_INDEX
| SAI_QUEUE_ATTR_PAUSE_STATUS
| SAI_QUEUE_ATTR_PAUSE_STATUS_last
| SAI_QUEUE_ATTR_TYPE
| SAI_QUEUE_ATTR_WRED_PROFILE_ID
| SAI_QUEUE_STAT_BYTES
| SAI_QUEUE_STAT_CURR_OCCUPANCY_BYTES
| SAI_QUEUE_STAT_DROPPED_BYTES
| SAI_QUEUE_STAT_DROPPED_PACKETS
| SAI_QUEUE_STAT_PACKETS
| SAI_QUEUE_STAT_PACKETS_last
| SAI_QUEUE_STAT_SHARED_WATERMARK_BYTES
| SAI_QUEUE_TYPE_ALL
| SAI_QUEUE_TYPE_MULTICAST
| SAI_QUEUE_TYPE_UNICAST
| SAI_REDIS_NOTIFY_SYNCD_APPLY_VIEW
| SAI_REDIS_NOTIFY_SYNCD_INIT_VIEW
| SAI_REDIS_SWITCH_ATTR_FLUSH
| SAI_REDIS_SWITCH_ATTR_NOTIFY_SYNCD
| SAI_REDIS_SWITCH_ATTR_PERFORM_LOG_ROTATE
| SAI_REDIS_SWITCH_ATTR_RECORD
| SAI_REDIS_SWITCH_ATTR_RECORDING_OUTPUT_DIR
| SAI_REDIS_SWITCH_ATTR_USE_PIPELINE
| SAI_ROUTE_ATTR_PACKET_ACTION
| SAI_ROUTE_ENTRY_ATTR_NEXT_HOP_ID
| SAI_ROUTE_ENTRY_ATTR_PACKET_ACTION
| SAI_ROUTER_INTERFACE_ATTR_BRIDGE_ID
| SAI_ROUTER_INTERFACE_ATTR_MTU
| SAI_ROUTER_INTERFACE_ATTR_PORT_ID
| SAI_ROUTER_INTERFACE_ATTR_SRC_MAC_ADDRESS
| SAI_ROUTER_INTERFACE_ATTR_TYPE
| SAI_ROUTER_INTERFACE_ATTR_VIRTUAL_ROUTER_ID
| SAI_ROUTER_INTERFACE_ATTR_VLAN_ID
| SAI_ROUTER_INTERFACE_STAT_IN_ERROR_OCTETS
| SAI_ROUTER_INTERFACE_STAT_IN_ERROR_PACKETS
| SAI_ROUTER_INTERFACE_STAT_IN_OCTETS
| SAI_ROUTER_INTERFACE_STAT_IN_PACKETS
| SAI_ROUTER_INTERFACE_STAT_OUT_ERROR_OCTETS
| SAI_ROUTER_INTERFACE_STAT_OUT_ERROR_PACKETS
| SAI_ROUTER_INTERFACE_STAT_OUT_OCTETS
| SAI_ROUTER_INTERFACE_STAT_OUT_PACKETS
| SAI_ROUTER_INTERFACE_TYPE_BRIDGE
| SAI_ROUTER_INTERFACE_TYPE_LOOPBACK
| SAI_ROUTER_INTERFACE_TYPE_PORT
| SAI_ROUTER_INTERFACE_TYPE_VLAN
| SAI_SCHEDULER_ATTR_SCHEDULING_TYPE
| SAI_SCHEDULER_ATTR_SCHEDULING_WEIGHT
| SAI_SCHEDULER_GROUP_ATTR_CHILD_COUNT
| SAI_SCHEDULER_GROUP_ATTR_CHILD_LIST
| SAI_SCHEDULER_GROUP_ATTR_SCHEDULER_PROFILE_ID
| SAI_SCHEDULING_TYPE_DWRR
| SAI_SCHEDULING_TYPE_STRICT
| SAI_SCHEDULING_TYPE_WRR
| SAI_STATUS_BUFFER_OVERFLOW
| SAI_STATUS_FAILURE
| SAI_STATUS_IS_ATTR_NOT_IMPLEMENTED
| SAI_STATUS_IS_ATTR_NOT_SUPPORTED
| SAI_STATUS_ITEM_NOT_FOUND
| SAI_STATUS_NOT_IMPLEMENTED
| SAI_STATUS_SUCCESS
| SAI_SWITCH_ATTR_ACL_ENTRY_MAXIMUM_PRIORITY
| SAI_SWITCH_ATTR_ACL_ENTRY_MINIMUM_PRIORITY
| SAI_SWITCH_ATTR_AVAILABLE_ACL_TABLE
| SAI_SWITCH_ATTR_AVAILABLE_ACL_TABLE_GROUP
| SAI_SWITCH_ATTR_AVAILABLE_FDB_ENTRY
| SAI_SWITCH_ATTR_AVAILABLE_IPV4_NEIGHBOR_ENTRY
| SAI_SWITCH_ATTR_AVAILABLE_IPV4_NEXTHOP_ENTRY
| SAI_SWITCH_ATTR_AVAILABLE_IPV4_ROUTE_ENTRY
| SAI_SWITCH_ATTR_AVAILABLE_IPV6_NEIGHBOR_ENTRY
| SAI_SWITCH_ATTR_AVAILABLE_IPV6_NEXTHOP_ENTRY
| SAI_SWITCH_ATTR_AVAILABLE_IPV6_ROUTE_ENTRY
| SAI_SWITCH_ATTR_AVAILABLE_NEXT_HOP_GROUP_ENTRY
| SAI_SWITCH_ATTR_AVAILABLE_NEXT_HOP_GROUP_MEMBER_ENTRY
| SAI_SWITCH_ATTR_CPU_PORT
| SAI_SWITCH_ATTR_CUSTOM_RANGE_BASE
| SAI_SWITCH_ATTR_CUSTOM_RANGE_START
| SAI_SWITCH_ATTR_DEFAULT_1Q_BRIDGE_ID
| SAI_SWITCH_ATTR_DEFAULT_TRAP_GROUP
| SAI_SWITCH_ATTR_DEFAULT_VIRTUAL_ROUTER_ID
| SAI_SWITCH_ATTR_DEFAULT_VLAN_ID
| SAI_SWITCH_ATTR_ECMP_DEFAULT_HASH_SEED
| SAI_SWITCH_ATTR_FDB_AGING_TIME
| SAI_SWITCH_ATTR_FDB_BROADCAST_MISS_PACKET_ACTION
| SAI_SWITCH_ATTR_FDB_EVENT_NOTIFY
| SAI_SWITCH_ATTR_FDB_MULTICAST_MISS_PACKET_ACTION
| SAI_SWITCH_ATTR_FDB_UNICAST_MISS_PACKET_ACTION
| SAI_SWITCH_ATTR_INIT_SWITCH
| SAI_SWITCH_ATTR_LAG_DEFAULT_HASH_SEED
| SAI_SWITCH_ATTR_NUMBER_OF_ECMP_GROUPS
| SAI_SWITCH_ATTR_PORT_LIST
| SAI_SWITCH_ATTR_PORT_MAX_MTU
| SAI_SWITCH_ATTR_PORT_NUMBER
| SAI_SWITCH_ATTR_PORT_STATE_CHANGE_NOTIFY
| SAI_SWITCH_ATTR_SHUTDOWN_REQUEST_NOTIFY
| SAI_SWITCH_ATTR_SRC_MAC_ADDRESS
| SAI_SWITCH_ATTR_VXLAN_DEFAULT_PORT
| SAI_SWITCH_ATTR_VXLAN_DEFAULT_ROUTER_MAC
| SAI_TABLE_BITMAP_CLASSIFICATION_ENTRY_ACTION_SET_METADATA
| SAI_TABLE_BITMAP_CLASSIFICATION_ENTRY_ATTR_ACTION
| SAI_TABLE_BITMAP_CLASSIFICATION_ENTRY_ATTR_IN_RIF_METADATA
| SAI_TABLE_BITMAP_CLASSIFICATION_ENTRY_ATTR_ROUTER_INTERFACE_KEY
| SAI_TABLE_BITMAP_ROUTER_ENTRY_ACTION_TO_LOCAL
| SAI_TABLE_BITMAP_ROUTER_ENTRY_ACTION_TO_NEXTHOP
| SAI_TABLE_BITMAP_ROUTER_ENTRY_ATTR_ACTION
| SAI_TABLE_BITMAP_ROUTER_ENTRY_ATTR_DST_IP_KEY
| SAI_TABLE_BITMAP_ROUTER_ENTRY_ATTR_IN_RIF_METADATA_KEY
| SAI_TABLE_BITMAP_ROUTER_ENTRY_ATTR_IN_RIF_METADATA_MASK
| SAI_TABLE_BITMAP_ROUTER_ENTRY_ATTR_NEXT_HOP
| SAI_TABLE_BITMAP_ROUTER_ENTRY_ATTR_PRIORITY
| SAI_TABLE_BITMAP_ROUTER_ENTRY_ATTR_ROUTER_INTERFACE
| SAI_TUNNEL_ATTR_DECAP_DSCP_MODE
| SAI_TUNNEL_ATTR_DECAP_ECN_MODE
| SAI_TUNNEL_ATTR_DECAP_MAPPERS
| SAI_TUNNEL_ATTR_DECAP_TTL_MODE
| SAI_TUNNEL_ATTR_ENCAP_MAPPERS
| SAI_TUNNEL_ATTR_ENCAP_SRC_IP
| SAI_TUNNEL_ATTR_OVERLAY_INTERFACE
| SAI_TUNNEL_ATTR_TYPE
| SAI_TUNNEL_ATTR_UNDERLAY_INTERFACE
| SAI_TUNNEL_DECAP_ECN_MODE_COPY_FROM_OUTER
| SAI_TUNNEL_DECAP_ECN_MODE_STANDARD
| SAI_TUNNEL_DSCP_MODE_PIPE_MODEL
| SAI_TUNNEL_DSCP_MODE_UNIFORM_MODEL
| SAI_TUNNEL_MAP_ATTR_TYPE
| SAI_TUNNEL_MAP_ENTRY_ATTR_BRIDGE_ID_KEY
| SAI_TUNNEL_MAP_ENTRY_ATTR_BRIDGE_ID_VALUE
| SAI_TUNNEL_MAP_ENTRY_ATTR_TUNNEL_MAP
| SAI_TUNNEL_MAP_ENTRY_ATTR_TUNNEL_MAP_TYPE
| SAI_TUNNEL_MAP_ENTRY_ATTR_VIRTUAL_ROUTER_ID_KEY
| SAI_TUNNEL_MAP_ENTRY_ATTR_VIRTUAL_ROUTER_ID_VALUE
| SAI_TUNNEL_MAP_ENTRY_ATTR_VLAN_ID_KEY
| SAI_TUNNEL_MAP_ENTRY_ATTR_VLAN_ID_VALUE
| SAI_TUNNEL_MAP_ENTRY_ATTR_VNI_ID_KEY
| SAI_TUNNEL_MAP_ENTRY_ATTR_VNI_ID_VALUE
| SAI_TUNNEL_MAP_TYPE_BRIDGE_IF_TO_VNI
| SAI_TUNNEL_MAP_TYPE_VIRTUAL_ROUTER_ID_TO_VNI
| SAI_TUNNEL_MAP_TYPE_VLAN_ID_TO_VNI
| SAI_TUNNEL_MAP_TYPE_VNI_TO_BRIDGE_IF
| SAI_TUNNEL_MAP_TYPE_VNI_TO_VIRTUAL_ROUTER_ID
| SAI_TUNNEL_MAP_TYPE_VNI_TO_VLAN_ID
| SAI_TUNNEL_TERM_TABLE_ENTRY_ATTR_ACTION_TUNNEL_ID
| SAI_TUNNEL_TERM_TABLE_ENTRY_ATTR_DST_IP
| SAI_TUNNEL_TERM_TABLE_ENTRY_ATTR_SRC_IP
| SAI_TUNNEL_TERM_TABLE_ENTRY_ATTR_TUNNEL_TYPE
| SAI_TUNNEL_TERM_TABLE_ENTRY_ATTR_TYPE
| SAI_TUNNEL_TERM_TABLE_ENTRY_ATTR_VR_ID
| SAI_TUNNEL_TERM_TABLE_ENTRY_TYPE_P2MP
| SAI_TUNNEL_TERM_TABLE_ENTRY_TYPE_P2P
| SAI_TUNNEL_TTL_MODE_PIPE_MODEL
| SAI_TUNNEL_TTL_MODE_UNIFORM_MODEL
| SAI_TUNNEL_TYPE_IPINIP
| SAI_TUNNEL_TYPE_VXLAN
| SAI_VIRTUAL_ROUTER_ATTR_ADMIN_V4_STATE
| SAI_VIRTUAL_ROUTER_ATTR_ADMIN_V6_STATE
| SAI_VIRTUAL_ROUTER_ATTR_SRC_MAC_ADDRESS
| SAI_VIRTUAL_ROUTER_ATTR_UNKNOWN_L3_MULTICAST_PACKET_ACTION
| SAI_VIRTUAL_ROUTER_ATTR_VIOLATION_IP_OPTIONS_PACKET_ACTION
| SAI_VIRTUAL_ROUTER_ATTR_VIOLATION_TTL1_PACKET_ACTION
| SAI_VLAN_ATTR_EGRESS_ACL
| SAI_VLAN_ATTR_INGRESS_ACL
| SAI_VLAN_ATTR_MEMBER_LIST
| SAI_VLAN_ATTR_VLAN_ID
| SAI_VLAN_MEMBER_ATTR_BRIDGE_PORT_ID
| SAI_VLAN_MEMBER_ATTR_VLAN_ID
| SAI_VLAN_MEMBER_ATTR_VLAN_TAGGING_MODE
| SAI_VLAN_TAGGING_MODE_PRIORITY_TAGGED
| SAI_VLAN_TAGGING_MODE_TAGGED
| SAI_VLAN_TAGGING_MODE_UNTAGGED
| SAI_VS_UNITTEST_CHANNEL
| SAI_WRED_ATTR_ECN_MARK_MODE
| SAI_WRED_ATTR_GREEN_DROP_PROBABILITY
| SAI_WRED_ATTR_GREEN_ENABLE
| SAI_WRED_ATTR_GREEN_MAX_THRESHOLD
| SAI_WRED_ATTR_GREEN_MIN_THRESHOLD
| SAI_WRED_ATTR_RED_DROP_PROBABILITY
| SAI_WRED_ATTR_RED_ENABLE
| SAI_WRED_ATTR_RED_MAX_THRESHOLD
| SAI_WRED_ATTR_RED_MIN_THRESHOLD
| SAI_WRED_ATTR_WEIGHT
| SAI_WRED_ATTR_YELLOW_DROP_PROBABILITY
| SAI_WRED_ATTR_YELLOW_ENABLE
| SAI_WRED_ATTR_YELLOW_MAX_THRESHOLD
| SAI_WRED_ATTR_YELLOW_MIN_THRESHOLD


