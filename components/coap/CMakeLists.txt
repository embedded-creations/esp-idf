set(COMPONENT_ADD_INCLUDEDIRS port/include port/include/coap libcoap/include libcoap/include/coap2)

set(COMPONENT_SRCS "libcoap/src/address.c"
                   "libcoap/src/async.c"
                   "libcoap/src/block.c"
                   "libcoap/src/coap_event.c"
                   "libcoap/src/coap_hashkey.c"
                   "libcoap/src/coap_session.c"
                   "libcoap/src/coap_time.c"
                   "libcoap/src/coap_debug.c"
                   "libcoap/src/encode.c"
                   "libcoap/src/mem.c"
                   "libcoap/src/net.c"
                   "libcoap/src/option.c"
                   "libcoap/src/pdu.c"
                   "libcoap/src/resource.c"
                   "libcoap/src/str.c"
                   "libcoap/src/subscribe.c"
                   "libcoap/src/uri.c"
                   "libcoap/src/coap_notls.c"
                   "port/coap_io.c")

set(COMPONENT_REQUIRES lwip)

register_component()

# Needed for coap headers in public builds, also.
#
# TODO: find a way to move this to a port header
target_compile_definitions(${COMPONENT_TARGET} PUBLIC WITH_POSIX)

