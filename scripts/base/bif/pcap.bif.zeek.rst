:tocdepth: 3

base/bif/pcap.bif.zeek
======================
.. zeek:namespace:: GLOBAL
.. zeek:namespace:: Pcap


:Namespaces: GLOBAL, Pcap

Summary
~~~~~~~
Functions
#########
=============================================================== ======================================================================
:zeek:id:`Pcap::error`: :zeek:type:`function`                   Returns a string representation of the last PCAP error.
:zeek:id:`Pcap::findalldevs`: :zeek:type:`function`             
:zeek:id:`Pcap::get_filter_state`: :zeek:type:`function`        Returns the initialization state of a PCAP filter, or OK if the either
                                                                there's no active packet source or the pcap filter ID does not exist.
:zeek:id:`Pcap::get_filter_state_string`: :zeek:type:`function` Returns a string containing any error messages that were reported by
                                                                filter initialization.
:zeek:id:`Pcap::install_pcap_filter`: :zeek:type:`function`     Installs a PCAP filter that has been precompiled with
                                                                :zeek:id:`Pcap::precompile_pcap_filter`.
:zeek:id:`Pcap::precompile_pcap_filter`: :zeek:type:`function`  Precompiles a PCAP filter and binds it to a given identifier.
=============================================================== ======================================================================


Detailed Interface
~~~~~~~~~~~~~~~~~~
Functions
#########
.. zeek:id:: Pcap::error
   :source-code: base/bif/pcap.bif.zeek 69 69

   :Type: :zeek:type:`function` () : :zeek:type:`string`

   Returns a string representation of the last PCAP error.
   

   :returns: A descriptive error message of the PCAP function that failed.
   
   .. zeek:see:: Pcap::precompile_pcap_filter
                Pcap::install_pcap_filter
                install_src_addr_filter
                install_src_net_filter
                uninstall_src_addr_filter
                uninstall_src_net_filter
                install_dst_addr_filter
                install_dst_net_filter
                uninstall_dst_addr_filter
                uninstall_dst_net_filter

.. zeek:id:: Pcap::findalldevs
   :source-code: base/bif/pcap.bif.zeek 99 99

   :Type: :zeek:type:`function` () : :zeek:type:`Pcap::Interfaces`


.. zeek:id:: Pcap::get_filter_state
   :source-code: base/bif/pcap.bif.zeek 82 82

   :Type: :zeek:type:`function` (id: :zeek:type:`PcapFilterID`) : :zeek:type:`Pcap::filter_state`

   Returns the initialization state of a PCAP filter, or OK if the either
   there's no active packet source or the pcap filter ID does not exist.
   

   :id: The PCAP filter id of a precompiled filter.
   

   :returns: A state value denoting whether any warnings or errors were
            encountered while initializing the filter.
   
   .. zeek:see:: Pcap::precompile_pcap_filter
                 Pcap::install_pcap_filter

.. zeek:id:: Pcap::get_filter_state_string
   :source-code: base/bif/pcap.bif.zeek 96 96

   :Type: :zeek:type:`function` (id: :zeek:type:`PcapFilterID`) : :zeek:type:`string`

   Returns a string containing any error messages that were reported by
   filter initialization.
   

   :id: The PCAP filter id of a precompiled filter.
   

   :returns: Warning/error strings from the initialization process, a blank
            string if none were encountered, or '<unknown>' if either there
            is no active packet source or the filter ID doesn't exist.
   
   .. zeek:see:: Pcap::precompile_pcap_filter
                 Pcap::install_pcap_filter

.. zeek:id:: Pcap::install_pcap_filter
   :source-code: base/bif/pcap.bif.zeek 52 52

   :Type: :zeek:type:`function` (id: :zeek:type:`PcapFilterID`) : :zeek:type:`bool`

   Installs a PCAP filter that has been precompiled with
   :zeek:id:`Pcap::precompile_pcap_filter`.
   

   :id: The PCAP filter id of a precompiled filter.
   

   :returns: True if the filter associated with *id* has been installed
            successfully.
   
   .. zeek:see:: Pcap::precompile_pcap_filter
                install_src_addr_filter
                install_src_net_filter
                uninstall_src_addr_filter
                uninstall_src_net_filter
                install_dst_addr_filter
                install_dst_net_filter
                uninstall_dst_addr_filter
                uninstall_dst_net_filter
                Pcap::error

.. zeek:id:: Pcap::precompile_pcap_filter
   :source-code: base/bif/pcap.bif.zeek 31 31

   :Type: :zeek:type:`function` (id: :zeek:type:`PcapFilterID`, s: :zeek:type:`string`) : :zeek:type:`bool`

   Precompiles a PCAP filter and binds it to a given identifier.
   

   :id: The PCAP identifier to reference the filter *s* later on.
   

   :s: The PCAP filter. See ``man tcpdump`` for valid expressions.
   

   :returns: True if *s* is valid and precompiles successfully.
   
   .. zeek:see:: Pcap::install_pcap_filter
            install_src_addr_filter
            install_src_net_filter
            uninstall_src_addr_filter
            uninstall_src_net_filter
            install_dst_addr_filter
            install_dst_net_filter
            uninstall_dst_addr_filter
            uninstall_dst_net_filter
            Pcap::error


