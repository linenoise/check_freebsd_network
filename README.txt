NAME
    check_freebsd_network - Nagios plugin to report on FreeBSD network
    statistics

DESCRIPTION
    This script acts as a plugin module for the Nagios IT infrastructure
    monitoring system. It on a FreeBSD server to pull network status
    information from netstat(1). This plugin reports on the following 322
    network statistics:

    *   icmp6_address_unreachable_errors
    *   icmp6_administratively_prohibited_errors
    *   icmp6_bad_checksums
    *   icmp6_bad_neighbor_advertisement_messages
    *   icmp6_bad_neighbor_solicitation_messages
    *   icmp6_bad_redirect_messages
    *   icmp6_bad_router_advertisement_messages
    *   icmp6_bad_router_solicitation_messages
    *   icmp6_beyond_scope_errors
    *   icmp6_calls_to_icmp_error
    *   icmp6_echo_input
    *   icmp6_echo_output
    *   icmp6_echo_reply_input
    *   icmp6_echo_reply_output
    *   icmp6_erroneous_header_field_errors
    *   icmp6_errors_not_generated_because_of_rate_limitation
    *   icmp6_errors_not_generated_in_response_to_an_icmp_message
    *   icmp6_message_response_generated
    *   icmp6_messages_less_than_minimum_length
    *   icmp6_messages_with_bad_ND_options
    *   icmp6_messages_with_bad_code_fields
    *   icmp6_messages_with_bad_length
    *   icmp6_messages_with_too_many_ND_options
    *   icmp6_multicast_listener_report_output
    *   icmp6_no_route_errors
    *   icmp6_packet_too_big_errors
    *   icmp6_path_MTU_changes
    *   icmp6_port_unreachable_errors
    *   icmp6_redirect_errors
    *   icmp6_time_exceed_reassembly_errors
    *   icmp6_time_exceed_transit_errors
    *   icmp6_unknown_errors
    *   icmp6_unrecognized_next_header_errors
    *   icmp6_unrecognized_option_errors
    *   icmp_ICMP_address_mask_responses_are_disabled
    *   icmp_bad_checksums
    *   icmp_calls_to_icmp_error
    *   icmp_destination_unreachable_input
    *   icmp_destination_unreachable_output
    *   icmp_echo_input
    *   icmp_echo_reply_input
    *   icmp_echo_reply_output
    *   icmp_errors_not_generated_in_response_to_an_icmp_message
    *   icmp_invalid_return_addresses
    *   icmp_message_responses_generated
    *   icmp_messages_less_than_minimum_length
    *   icmp_messages_with_bad_code_fields
    *   icmp_messages_with_bad_length
    *   icmp_multicast_echo_requests_ignored
    *   icmp_multicast_timestamp_requests_ignored
    *   icmp_no_return_routes
    *   icmp_routing_redirect_input
    *   icmp_time_exceeded_input
    *   igmp_membership_queries_received
    *   igmp_membership_queries_received_with_invalid_field
    *   igmp_membership_reports_received
    *   igmp_membership_reports_received_for_groups_to_which_we_belong
    *   igmp_membership_reports_received_with_invalid_field
    *   igmp_membership_reports_sent
    *   igmp_messages_received
    *   igmp_messages_received_with_bad_checksum
    *   igmp_messages_received_with_too_few_bytes
    *   ip6_ICMP_input
    *   ip6_TCP_input
    *   ip6_datagrams_that_cant_be_fragmented
    *   ip6_failures_of_source_address_selection
    *   ip6_forward_cache_hit
    *   ip6_forward_cache_miss
    *   ip6_fragments_created
    *   ip6_fragments_dropped_after_timeout
    *   ip6_fragments_dropped_for_dup_or_out_of_space
    *   ip6_fragments_received
    *   ip6_fragments_that_exceeded_limit
    *   ip6_multicast_packets_which_we_dont_join
    *   ip6_one_ext_mbuf
    *   ip6_one_mbuf
    *   ip6_output_datagrams_fragmented
    *   ip6_output_packets_discarded_due_to_no_route
    *   ip6_output_packets_dropped
    *   ip6_packets_discarded_because_of_too_many_headers
    *   ip6_packets_for_this_host
    *   ip6_packets_forwarded
    *   ip6_packets_not_forwardable
    *   ip6_packets_reassembled_ok
    *   ip6_packets_received_with_data_size_less_than_data_length
    *   ip6_packets_received_with_size_smaller_than_minimum
    *   ip6_packets_sent_from_this_host
    *   ip6_packets_sent_with_fabricated_ip_header
    *   ip6_packets_that_violated_scope_rules
    *   ip6_packets_whose_headers_are_not_continuous
    *   ip6_redirects_sent
    *   ip6_source_address_selection_rule_first_candidate
    *   ip6_source_address_selection_rule_same_address
    *   ip6_total_packets_received
    *   ip6_tunneling_packets_that_cant_find_gif
    *   ip6_two_or_more_ext_mbuf
    *   ip6_with_bad_options
    *   ip6_with_incorrect_version_number
    *   ip_bad_header_checksums
    *   ip_datagrams_that_cant_be_fragmented
    *   ip_datagrams_with_bad_address_in_header
    *   ip_fragments_created
    *   ip_fragments_dropped_after_timeout
    *   ip_fragments_dropped_for_dup_or_out_of_space
    *   ip_fragments_received
    *   ip_output_datagrams_fragmented
    *   ip_output_packets_discarded_due_to_no_route
    *   ip_output_packets_dropped
    *   ip_packets_fast_forwarded
    *   ip_packets_for_this_host
    *   ip_packets_for_unknown_or_unsupported_protocol
    *   ip_packets_forwarded
    *   ip_packets_not_forwardable
    *   ip_packets_reassembled_ok
    *   ip_packets_received_for_unknown_multicast_group
    *   ip_packets_sent_from_this_host
    *   ip_packets_sent_with_fabricated_ip_header
    *   ip_redirects_sent
    *   ip_total_packets_received
    *   ip_tunneling_packets_that_cant_find_gif
    *   ip_with_bad_options
    *   ip_with_data_length_less_than_header_length
    *   ip_with_data_size_less_than_data_length
    *   ip_with_header_length_less_than_data_size
    *   ip_with_incorrect_version_number
    *   ip_with_ip_length_greater_than_max_ip_packet_size
    *   ip_with_size_smaller_than_minimum
    *   rip6_checksum_calcurations_on_inbound
    *   rip6_datagrams_output
    *   rip6_delivered
    *   rip6_messages_dropped_due_to_full_socket_buffers
    *   rip6_messages_dropped_due_to_no_socket
    *   rip6_messages_received
    *   rip6_messages_with_bad_checksum
    *   rip6_multicast_messages_dropped_due_to_no_socket
    *   sctp_FRs_that_happened_more_than_once_to_same_chunk_
    *   sctp_RFC813_allowed_sending
    *   sctp_RFC813_does_not_allow_sending
    *   sctp_bad_SID
    *   sctp_bad_v_tag
    *   sctp_cached_chunks_used
    *   sctp_cached_stream_oqs_used
    *   sctp_checksum_error
    *   sctp_collision_in_express_lookup_
    *   sctp_fast_retransmitted_DATA_chunks
    *   sctp_input_AUTH_chunks
    *   sctp_input_DATA_chunks
    *   sctp_input_ECNE_chunks
    *   sctp_input_HB_ACK_chunks
    *   sctp_input_HB_chunks
    *   sctp_input_SACK_chunks
    *   sctp_input_auth_failed
    *   sctp_input_chunks_missing_AUTH
    *   sctp_input_datagrams
    *   sctp_input_duplicate_DATA_chunks
    *   sctp_input_fast_path_multi_part_data
    *   sctp_input_fast_path_receives_all_one_chunk
    *   sctp_input_packets
    *   sctp_input_packets_that_had_data
    *   sctp_intput_HB_chunks
    *   sctp_invalid_HMAC_ids_received
    *   sctp_invalid_secret_ids_received
    *   sctp_ip_output_error_counter
    *   sctp_look_ahead_tells_us_no_memory_in_interface
    *   sctp_max_burst_dosnt_allow_sending
    *   sctp_no_endpoint_for_port
    *   sctp_no_memory
    *   sctp_number_of_in_data_drops_due_to_chunk_limit_reached
    *   sctp_number_of_in_data_drops_due_to_rwnd_limit_reached
    *   sctp_number_of_map_array_over_runs_via_fwd_tsns
    *   sctp_number_of_multiple_FR_in_a_RTT_window
    *   sctp_numbers_of_window_probes_sent
    *   sctp_output_AUTH_chunks
    *   sctp_output_DATA_chunks
    *   sctp_output_ECNE_chunks
    *   sctp_output_SACKs
    *   sctp_output_packets
    *   sctp_packet_dropped_TSN_s_marked_for_Fast_Retran
    *   sctp_packet_dropped_attempt_reverse_TSN_lookup
    *   sctp_packet_dropped_data_did_not_match_TSN
    *   sctp_packet_dropped_e_host_confirms_zero_rwnd
    *   sctp_packet_dropped_failed_to_find_TSN
    *   sctp_packet_dropped_from_end_host
    *   sctp_packet_dropped_from_middle_box
    *   sctp_packet_dropped_midbox_confirms_no_space
    *   sctp_packet_dropped_non_data_non_endhost
    *   sctp_packet_dropped_non_endhost_bandwidth_rep_only
    *   sctp_packet_dropped_not_enough_data_to_confirm
    *   sctp_packet_dropped_not_enough_for_chunk_header
    *   sctp_packet_dropped_where_process_chunk_drop_said_break
    *   sctp_packet_dropped_with_data
    *   sctp_packet_shorter_than_header
    *   sctp_retransmitted_DATA_chunks
    *   sctp_sacks_the_slow_way
    *   sctp_same_for_above
    *   sctp_send_burst_avoidance_already_max_burst_inflight_to_net
    *   sctp_send_cwnd_full_avoidance_already_max_burst_inflight_to_net
    *   sctp_sends_with_ABORT_flag_set
    *   sctp_sends_with_EOF_flag_set
    *   sctp_sends_with_sinfo_nonzero_flags
    *   sctp_timeouts_INIT_timers_fired
    *   sctp_timeouts_PMTU_timers_fired
    *   sctp_timeouts_T3_data_time_outs
    *   sctp_timeouts_a_cookie_timeout_fired
    *   sctp_timeouts_an_asconf_timer_fired
    *   sctp_timeouts_an_endpoint_changed_its_cookiesecret
    *   sctp_timeouts_asoc_free_timers_expired
    *   sctp_timeouts_auto_close_timer_fired
    *   sctp_timeouts_early_FR_timers_fired
    *   sctp_timeouts_heartbeat_timers_fired
    *   sctp_timeouts_inp_free_timers_expired
    *   sctp_timeouts_iterator_timers_fired
    *   sctp_timeouts_sack_timers_fired
    *   sctp_timeouts_shutdown_ack_timers_fired
    *   sctp_timeouts_shutdown_guard_timers_fired
    *   sctp_timeouts_shutdown_timers_fired
    *   sctp_timeouts_stream_reset_timers_fired
    *   sctp_timeouts_window_probe_timers_fired
    *   sctp_times_a_ECN_reduced_the_cwnd
    *   sctp_times_an_output_error_to_clamp_down_on_next_user_send
    *   sctp_times_protocol_drain_called
    *   sctp_times_recv_was_called_with_peek
    *   sctp_times_sctp_senderrors_were_caused_from_a_user
    *   sctp_times_the_sender_ran_dry_of_user_data_on_primary
    *   sctp_times_we_did_a_protocol_drain
    *   sctp_unordered_sends
    *   sctp_unread_messages_abandonded_by_close
    *   sctp_used_express_lookup_via_vtag
    *   sctp_window_update_only_sacks_sent
    *   tcp_SACK_options_received
    *   tcp_SACK_options_sent
    *   tcp_SACK_recovery_episodes
    *   tcp_SACK_scoreboard_overflow
    *   tcp_bad_connection_attempts
    *   tcp_byte_rexmits_in_SACK_recovery_episodes
    *   tcp_connection_accepts
    *   tcp_connection_requests
    *   tcp_connections_closed
    *   tcp_connections_dropped
    *   tcp_connections_dropped_because_of_timeout
    *   tcp_connections_dropped_by_keepalive
    *   tcp_connections_dropped_by_persist_timeout
    *   tcp_connections_dropped_by_rexmit_timeout
    *   tcp_connections_established_including_accepts
    *   tcp_connections_updated_cached_RTT_on_close
    *   tcp_connections_updated_cached_RTT_variance_on_close
    *   tcp_connections_updated_cached_ssthresh_on_close
    *   tcp_cookies_received
    *   tcp_cookies_sent
    *   tcp_correct_ACK_header_predictions
    *   tcp_correct_data_packet_header_predictions
    *   tcp_embryonic_connections_dropped
    *   tcp_ignored_RSTs_in_the_windows
    *   tcp_keepalive_probes_sent
    *   tcp_keepalive_timeouts
    *   tcp_listen_queue_overflows
    *   tcp_packets_received
    *   tcp_packets_sent
    *   tcp_persist_timeouts
    *   tcp_received_acks
    *   tcp_received_acks_for_unsent_data
    *   tcp_received_acks_within_bytes
    *   tcp_received_bytes_in_sequence
    *   tcp_received_bytes_of_data_after_window
    *   tcp_received_completely_duplicate_packets
    *   tcp_received_completely_duplicate_packets_byte_total
    *   tcp_received_duplicate_acks
    *   tcp_received_old_duplicate_packets
    *   tcp_received_out_of_order_packets
    *   tcp_received_out_of_order_packets_byte_total
    *   tcp_received_packets_discarded_because_packet_too_short
    *   tcp_received_packets_discarded_due_to_memory_problems
    *   tcp_received_packets_discarded_for_bad_checksums
    *   tcp_received_packets_discarded_for_bad_header_offset_fields
    *   tcp_received_packets_in_sequence
    *   tcp_received_packets_of_data_after_window
    *   tcp_received_packets_received_after_close
    *   tcp_received_packets_with_some_dup_data
    *   tcp_received_packets_with_some_dup_data_bytes_total
    *   tcp_received_window_probes
    *   tcp_received_window_update_packets
    *   tcp_retransmit_timeouts
    *   tcp_segment_rexmits_in_SACK_recovery_episodes
    *   tcp_segments_update_rtt_attempts
    *   tcp_segments_updated_rtt
    *   tcp_sent_URG_only_packets
    *   tcp_sent_ack_only_packets
    *   tcp_sent_ack_only_packets_delayed
    *   tcp_sent_control_packets
    *   tcp_sent_data_bytes
    *   tcp_sent_data_bytes_retransmitted
    *   tcp_sent_data_packets
    *   tcp_sent_data_packets_retransmitted
    *   tcp_sent_data_packets_unnecessarily_retransmitted
    *   tcp_sent_resends_initiated_by_MTU_discovery
    *   tcp_sent_window_probe_packets
    *   tcp_sent_window_update_packets
    *   tcp_syncache_entries_aborted
    *   tcp_syncache_entries_added
    *   tcp_syncache_entries_badack
    *   tcp_syncache_entries_bucket_overflow
    *   tcp_syncache_entries_cache_overflow
    *   tcp_syncache_entries_completed
    *   tcp_syncache_entries_dropped
    *   tcp_syncache_entries_dupsyn
    *   tcp_syncache_entries_reset
    *   tcp_syncache_entries_retransmitted
    *   tcp_syncache_entries_stale
    *   tcp_syncache_entries_unreach
    *   tcp_syncache_entries_zone_failures
    *   udp_broadcast_multicast_datagrams_undelivered
    *   udp_datagrams_output
    *   udp_datagrams_received
    *   udp_delivered
    *   udp_dropped_due_to_full_socket_buffers
    *   udp_dropped_due_to_no_socket
    *   udp_dropped_not_for_hashed_pcb
    *   udp_times_multicast_source_filter_matched
    *   udp_with_bad_checksum
    *   udp_with_bad_data_length_field
    *   udp_with_incomplete_header
    *   udp_with_no_checksum

    This has been tested with FreeBSD 7.1.

SYNOPSIS
  Command Line Interface
    Get the total number of TCP packets discarded for bad header checksums:

            check_freebsd_network -m tcp_received_packets_discarded_for_bad_checksums -w 100 -c 1000

    Get the number of IP packets received for an unknown or unsupported
    protocol:

            check_freebsd_network -m ip_packets_for_unknown_or_unsupported_protocol -w 1000 -c 10000

    Get the number of ICMP messages with bad code fields:

            check_freebsd_network -m icmp_messages_with_bad_code_fields -w 100 -c 1000

    Run this script with command line options stored in a configuration
    file:

            check_freebsd_network --extra-opts=my_config.ini

SEE ALSO
    If using an external configuration file, it should be structured
    according to the specification at
    <http://nagiosplugins.org/extra-opts/>.

    Thresholds given to this script should be in the format specified at
    <http://nagiosplug.sourceforge.net/developer-guidelines.html>.

    This module is built upon Nagios::Plugin by the Nagios Plugin
    Development Team. Further reading on Nagios, NPRE, and Nagios Plugins is
    available at <http://nagios.com/>.

AUTHOR
    This script is written and maintained by Dann Stayskal
    <dann@stayskal.com> and is available on his website, at
    <http://fragmentedzen.com/software/check_freebsd/>.

LICENSE
    Copyright (C) 2009 by Dann Stayskal.

    This program is free software; you can redistribute it and/or modify it
    under the terms of the GNU General Public License as published by the
    Free Software Foundation; either version 2 of the License, or (at your
    option) any later version.

    This program is distributed in the hope that it will be useful, but
    WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General
    Public License for more details.

    You should have received a copy of the GNU General Public License along
    with this program; if not, write to the Free Software Foundation, Inc.,
    59 Temple Place, Suite 330, Boston, MA 02111-1307 USA

    Nagios, the Nagios logo, and Nagios graphics are the servicemarks,
    trademarks, or registered trademarks owned by Nagios Enterprises. All
    other servicemarks and trademarks are the property of their respective
    owner.

