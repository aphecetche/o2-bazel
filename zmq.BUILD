load("@//:zmq.bzl","zmq_test","zmq_test_unity")

PLATFORM_HPP = """
#ifndef __ZMQ_PLATFORM_HPP_INCLUDED__
#define __ZMQ_PLATFORM_HPP_INCLUDED__

#define ZMQ_USE_KQUEUE
#define HAVE_FORK
#define HAVE_MKDTEMP
#define ZMQ_HAVE_UIO
#define ZMQ_HAVE_IFADDRS
#define ZMQ_HAVE_O_CLOEXEC
#define ZMQ_HAVE_SO_KEEPALIVE
#define ZMQ_HAVE_TCP_KEEPCNT
#define ZMQ_HAVE_TCP_KEEPINTVL
#define ZMQ_HAVE_TCP_KEEPALIVE
#define ZMQ_HAVE_PTHREAD_SETNAME_1
#define ZMQ_HAVE_CURVE
#define ZMQ_USE_TWEETNACL

#ifdef _AIX
  #define ZMQ_HAVE_AIX
#endif

#if defined ANDROID
  #define ZMQ_HAVE_ANDROID
#endif

#if defined __CYGWIN__
  #define ZMQ_HAVE_CYGWIN
#endif

#if defined __MINGW32__
  #define ZMQ_HAVE_MINGW32
#endif

#if defined(__FreeBSD__) || defined(__DragonFly__) || defined(__FreeBSD_kernel__)
  #define ZMQ_HAVE_FREEBSD
#endif

#if defined __hpux
  #define ZMQ_HAVE_HPUX
#endif

#if defined __linux__
  #define ZMQ_HAVE_LINUX
#endif

#if defined __NetBSD__
  #define ZMQ_HAVE_NETBSD
#endif

#if defined __OpenBSD__
  #define ZMQ_HAVE_OPENBSD
#endif

#if defined __VMS
  #define ZMQ_HAVE_OPENVMS
#endif

#if defined __APPLE__
  #define ZMQ_HAVE_OSX
#endif

#if defined __QNXNTO__
  #define ZMQ_HAVE_QNXNTO
#endif

#define ZOB

#if defined(sun) || defined(__sun)
  #define ZMQ_HAVE_SOLARIS
#endif

/* #undef ZMQ_HAVE_WINDOWS */
/* #undef ZMQ_HAVE_WINDOWS_UWP */

#endif
"""

genrule(
    name = "platform_hpp",
    outs = ["platform.hpp"],
    cmd = "".join([
        "echo '",
        PLATFORM_HPP,
        "' > $@",
    ]),
)

filegroup(
    name = "sources",
    srcs = [
        "src/precompiled.cpp",
        "src/address.cpp",
        "src/client.cpp",
        "src/clock.cpp",
        "src/ctx.cpp",
        "src/curve_mechanism_base.cpp",
        "src/curve_client.cpp",
        "src/curve_server.cpp",
        "src/dealer.cpp",
        "src/devpoll.cpp",
        "src/dgram.cpp",
        "src/dist.cpp",
        "src/epoll.cpp",
        "src/err.cpp",
        "src/fq.cpp",
        "src/io_object.cpp",
        "src/io_thread.cpp",
        "src/ip.cpp",
        "src/ipc_address.cpp",
        "src/ipc_connecter.cpp",
        "src/ipc_listener.cpp",
        "src/kqueue.cpp",
        "src/lb.cpp",
        "src/mailbox.cpp",
        "src/mailbox_safe.cpp",
        "src/mechanism.cpp",
        "src/mechanism_base.cpp",
        "src/metadata.cpp",
        "src/msg.cpp",
        "src/mtrie.cpp",
        "src/object.cpp",
        "src/options.cpp",
        "src/own.cpp",
        "src/null_mechanism.cpp",
        "src/pair.cpp",
        "src/pgm_receiver.cpp",
        "src/pgm_sender.cpp",
        "src/pgm_socket.cpp",
        "src/pipe.cpp",
        "src/plain_client.cpp",
        "src/plain_server.cpp",
        "src/poll.cpp",
        "src/poller_base.cpp",
        "src/pollset.cpp",
        "src/proxy.cpp",
        "src/pub.cpp",
        "src/pull.cpp",
        "src/push.cpp",
        "src/random.cpp",
        "src/raw_encoder.cpp",
        "src/raw_decoder.cpp",
        "src/reaper.cpp",
        "src/rep.cpp",
        "src/req.cpp",
        "src/router.cpp",
        "src/select.cpp",
        "src/server.cpp",
        "src/session_base.cpp",
        "src/signaler.cpp",
        "src/socket_base.cpp",
        "src/socks.cpp",
        "src/socks_connecter.cpp",
        "src/stream.cpp",
        "src/stream_engine.cpp",
        "src/sub.cpp",
        "src/tcp.cpp",
        "src/tcp_address.cpp",
        "src/tcp_connecter.cpp",
        "src/tcp_listener.cpp",
        "src/thread.cpp",
        "src/trie.cpp",
        "src/v1_decoder.cpp",
        "src/v1_encoder.cpp",
        "src/v2_decoder.cpp",
        "src/v2_encoder.cpp",
        "src/xpub.cpp",
        "src/xsub.cpp",
        "src/zmq.cpp",
        "src/zmq_utils.cpp",
        "src/decoder_allocators.cpp",
        "src/socket_poller.cpp",
        "src/timers.cpp",
        "src/radio.cpp",
        "src/dish.cpp",
        "src/udp_engine.cpp",
        "src/udp_address.cpp",
        "src/scatter.cpp",
        "src/gather.cpp",
		"src/zap_client.cpp",
		"src/address.hpp",
		"src/array.hpp",
		"src/atomic_counter.hpp",
		"src/atomic_ptr.hpp",
		"src/blob.hpp",
		"src/client.hpp",
		"src/clock.hpp",
		"src/command.hpp",
		"src/condition_variable.hpp",
		"src/config.hpp",
		"src/ctx.hpp",
		"src/curve_client.hpp",
		"src/curve_client_tools.hpp",
		"src/curve_mechanism_base.hpp",
		"src/curve_server.hpp",
		"src/dbuffer.hpp",
		"src/dealer.hpp",
		"src/decoder.hpp",
		"src/decoder_allocators.hpp",
		"src/devpoll.hpp",
		"src/dgram.hpp",
		"src/dish.hpp",
		"src/dist.hpp",
		"src/encoder.hpp",
		"src/epoll.hpp",
		"src/err.hpp",
		"src/fd.hpp",
		"src/fq.hpp",
		"src/gather.hpp",
		"src/generic_mtrie.hpp",
		"src/generic_mtrie_impl.hpp",
		"src/gssapi_client.hpp",
		"src/gssapi_mechanism_base.hpp",
		"src/gssapi_server.hpp",
		"src/i_decoder.hpp",
		"src/i_encoder.hpp",
		"src/i_engine.hpp",
		"src/i_mailbox.hpp",
		"src/i_poll_events.hpp",
		"src/io_object.hpp",
		"src/io_thread.hpp",
		"src/ip.hpp",
		"src/ipc_address.hpp",
		"src/ipc_connecter.hpp",
		"src/ipc_listener.hpp",
		"src/kqueue.hpp",
		"src/lb.hpp",
		"src/likely.hpp",
		"src/macros.hpp",
		"src/mailbox.hpp",
		"src/mailbox_safe.hpp",
		"src/mechanism.hpp",
		"src/mechanism_base.hpp",
		"src/metadata.hpp",
		"src/msg.hpp",
		"src/mtrie.hpp",
		"src/mutex.hpp",
		"src/norm_engine.hpp",
		"src/null_mechanism.hpp",
		"src/object.hpp",
		"src/options.hpp",
		"src/own.hpp",
		"src/pair.hpp",
		"src/pgm_receiver.hpp",
		"src/pgm_sender.hpp",
		"src/pgm_socket.hpp",
		"src/pipe.hpp",
		"src/plain_client.hpp",
		"src/plain_server.hpp",
		"src/poll.hpp",
		"src/poller.hpp",
		"src/poller_base.hpp",
		"src/pollset.hpp",
		"src/precompiled.hpp",
		"src/proxy.hpp",
		"src/pub.hpp",
		"src/pull.hpp",
		"src/push.hpp",
		"src/radio.hpp",
		"src/random.hpp",
		"src/raw_decoder.hpp",
		"src/raw_encoder.hpp",
		"src/reaper.hpp",
		"src/rep.hpp",
		"src/req.hpp",
		"src/router.hpp",
		"src/scatter.hpp",
		"src/select.hpp",
		"src/server.hpp",
		"src/session_base.hpp",
		"src/signaler.hpp",
		"src/socket_base.hpp",
		"src/socket_poller.hpp",
		"src/socks.hpp",
		"src/socks_connecter.hpp",
		"src/stdint.hpp",
		"src/stream.hpp",
		"src/stream_engine.hpp",
		"src/sub.hpp",
		"src/tcp.hpp",
		"src/tcp_address.hpp",
		"src/tcp_connecter.hpp",
		"src/tcp_listener.hpp",
		"src/thread.hpp",
		"src/timers.hpp",
		"src/tipc_address.hpp",
		"src/tipc_connecter.hpp",
		"src/tipc_listener.hpp",
		"src/trie.hpp",
		"src/udp_address.hpp",
		"src/udp_engine.hpp",
		"src/v1_decoder.hpp",
		"src/v1_encoder.hpp",
		"src/v2_decoder.hpp",
		"src/v2_encoder.hpp",
		"src/v2_protocol.hpp",
		"src/vmci.hpp",
		"src/vmci_address.hpp",
		"src/vmci_connecter.hpp",
		"src/vmci_listener.hpp",
		"src/windows.hpp",
		"src/wire.hpp",
		"src/xpub.hpp",
		"src/xsub.hpp",
		"src/ypipe.hpp",
		"src/ypipe_base.hpp",
		"src/ypipe_conflate.hpp",
		"src/yqueue.hpp",
		"src/zap_client.hpp",
        "src/zmq_draft.h",
        "src/tweetnacl.h",
		"src/tweetnacl.c"
    ],
)

cc_library(
    name = "zmq",
    srcs = [":platform_hpp"] + [":sources"],
    hdrs = [
        "include/zmq.h",
        "include/zmq_utils.h",
    ],
	includes = ["include"],
    visibility = ["//visibility:public"],
)

filegroup(
	name="testcommonsources",
	srcs=[":platform_hpp"]+["include/zmq.h"]
)

cc_library(
	name="unity",
	srcs=glob(["external/unity/*.h"])+glob(["external/unity/*.c"]),
	includes=["external/unity"]
)

zmq_test("test_ancillaries")
zmq_test("test_system")
zmq_test("test_pair_inproc")
zmq_test("test_pair_tcp")
zmq_test("test_reqrep_inproc")
zmq_test("test_hwm_pubsub")
zmq_test("test_reqrep_device")
zmq_test("test_sub_forward")
zmq_test("test_invalid_rep")
zmq_test("test_msg_flags")
zmq_test("test_msg_ffn")
zmq_test("test_term_endpoint")
zmq_test("test_probe_router")
zmq_test("test_stream")
zmq_test("test_stream_empty")
zmq_test("test_stream_disconnect")
zmq_test("test_disconnect_inproc")
zmq_test("test_unbind_inproc")
zmq_test("test_unbind_wildcard")
zmq_test("test_ctx_options")
zmq_test("test_security_null")
zmq_test("test_security_plain")
zmq_test("test_iov")
zmq_test("test_spec_req")
zmq_test("test_spec_rep")
zmq_test("test_spec_dealer")
zmq_test("test_spec_router")
zmq_test("test_spec_pushpull")
zmq_test("test_req_correlate")
zmq_test("test_req_relaxed")
zmq_test("test_inproc_connect")
zmq_test("test_issue_566")
zmq_test("test_shutdown_stress")
zmq_test("test_timeo")
zmq_test("test_many_sockets")
zmq_test("test_diffserv")
zmq_test("test_connect_rid")
zmq_test("test_xpub_nodrop")
zmq_test("test_pub_invert_matching")
zmq_test("test_setsockopt")
zmq_test("test_heartbeats")
zmq_test("test_atomics")
zmq_test("test_capabilities")
zmq_test("test_metadata")
zmq_test("test_srcfd")
zmq_test("test_stream_timeout")
zmq_test("test_xpub_manual")
zmq_test("test_xpub_welcome_msg")
zmq_test("test_base85")
zmq_test("test_sodium")

zmq_test_unity("test_bind_after_connect_tcp")
zmq_test_unity("test_connect_resolve")
zmq_test_unity("test_last_endpoint")
zmq_test_unity("test_bind_src_address")
zmq_test_unity("test_router_handover")
zmq_test_unity("test_reconnect_ivl")
zmq_test_unity("test_xpub_verbose")
zmq_test_unity("test_reqrep_tcp")
zmq_test_unity("test_ctx_destroy")
zmq_test_unity("test_sockopt_hwm")
zmq_test_unity("test_conflate")
zmq_test_unity("test_socket_null")
zmq_test_unity("test_hwm")
zmq_test_unity("test_router_mandatory")
zmq_test_unity("test_immediate")

# long one ?
zmq_test("test_security_zap",["tests/testutil_security.hpp"])


zmq_test("test_monitor",["tests/testutil_security.hpp"])