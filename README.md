# robot-ai
Control robot-arm to do AI feature testing

#
# Gesture Feature Test
#
"""  == Script working steps == 
1. Enable logger mode; Read configuration file
2. Enable USB port, set to 'sync mode'
3. Sync the UTC time between Device and PC
4. Get current UTC start time & current index; disable USB port, set to 'off mode'
5. Start testing
    - Pick up
    - Tilt
    - Double tap
            #Parameters to be used for testing from ssh remote command
            -s sample_test = 0 # example: 0: ST6DSO, 1: TDK, 2: ST6DSL, default: All
            -f force_test = 0 # 0: high force, 1: mid force, 2: lower force
            -p position_test = 3 # 0: upper, 1: mid, 2: lower, default: all
            -t times_test = 10 # Test times
    - ...others to be implemented.
6. Testing is done; Enable USB port, set to 'sync mode'
7. Get current UTC end time & current index; 
8. Parse the event logs
9. Count the test results and written into results files.
10. Generate charts and write into test reports
"""

"""
Type of gesture in data management
0x00: no gesture
0x01: double tap
The following gesture only in engineering build:
0x02: free fall
0x03: in rest
0x04: moving
0x05: pick-up
0x06: shake
0x07: single tap
0x08: tilt change
"""
