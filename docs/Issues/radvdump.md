#
# radvd configuration generated by radvdump 1.9.2
# based on Router Advertisement from fe80::d090:43ff:fed2:9519
# received by interface eth0
#

interface eth0
{
        AdvSendAdvert on;
        # Note: {Min,Max}RtrAdvInterval cannot 
	#       be obtained with radvdump
        AdvManagedFlag off;
        AdvOtherConfigFlag off;
        AdvReachableTime 0;
        AdvRetransTimer 0;
        AdvCurHopLimit 64;
        AdvDefaultLifetime 1800;
        AdvHomeAgentFlag off;
        AdvDefaultPreference medium;
        AdvSourceLLAddress on;

        prefix fd35:6225:4b8:6::/64
        {
                AdvValidLifetime 172800;
                AdvPreferredLifetime 172800;
                AdvOnLink on;
                AdvAutonomous on;
                AdvRouterAddr off;
        }; # End of prefix definition

}; # End of interface definition
