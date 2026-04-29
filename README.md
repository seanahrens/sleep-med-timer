
# sleep-med-timer

One-button bedside device firmware for the M5Stack ATOM Lite (primary) and
ATOM Echo (audio variant). A single press answers green ("OK to take a
sleep med") or red ("too late") based on a user-set 12-hour PM cutoff.
Hold gestures select between SET_BREAKPOINT (2s hold) and SET_HOUR (4s
hold) windows. Optional WiFi gives daily NTP + IP-geo timezone sync.

## Build
pio run # default: atom-lite (LED-only)
pio run -e atom-echo # adds I2S audio
pio run -t upload # flash the device

## Test (host-side, pure logic)
g++ -std=c++17 -Isrc tests/test_cutoff.cpp src/app_state.cpp -o /tmp/test_cutoff
/tmp/test_cutoff

