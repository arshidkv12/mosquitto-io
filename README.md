mosquitto-sys
=============

## Dependencies

`clang`  
`libmosquitto-dev`

Demode code 

```use std::os::raw::{c_char, c_int, c_void};

use mosquitto_io::{
    mosquitto_auth_check_password, mosquitto_auth_plugin_init, mosquitto_auth_unpwd_check,
    mosquitto_unpwd_check_callback, MOSQ_ERR_AUTH,
};

#[no_mangle]
pub extern "C" fn mosquitto_auth_plugin_init(
    user_data: *mut *mut c_void,
    opts: *const c_char,
    auth_cb: *mut mosquitto_auth_check_password,
    unauth_cb: *mut mosquitto_unpwd_check_callback,
) -> c_int {
    // Initialize your plugin here
    println!("Mosquitto authentication plugin initialized");
    MOSQ_ERR_SUCCESS
}
```
