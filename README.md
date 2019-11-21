# CubeMx-FreeRTOS-i2c-monitor

This code uses two gpio pins on the stm32f407 to monitor the i2c bus.
  - pd10 is configured as sda. (you can use any pin).
  - pd11 is configured as scl. (you can use any pin).
  
The i2c_monitor.c under src/i2c_monitor directory. 
  1. Create a instance of i2c monitor.
  
    static struct i2c_monitor_t i2c_mon;
    
  2. Call the i2c_mon_create to intialize the i2c_mon instance.
  
    i2c_mon_create(&i2c_mon);
    
  3. Assigned the sda and scl pin to the i2c_mon
  
    i2c_mon.sda_pin_set(&i2c_mon, GPIOD, GPIO_PIN_10);
    i2c_mon.scl_pin_set(&i2c_mon, GPIOD, GPIO_PIN_11);
   
  4. Connect the scl and sda to your DUT.
  5. Connect pc usb to CN5 of the stm32f407.
  6. When an i2c activity is detected, the log will be print out on VCOM port.
  
 Note: This code supports more one i2c monitor. Just create a new i2c monitor instance and add two new pins
 
  Have fun and enjoy.
