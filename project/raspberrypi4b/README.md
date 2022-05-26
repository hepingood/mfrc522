### 1. chip

#### 1.1 chip info

chip name : Raspberry Pi 4B

iic pin: SCL/SDA GPIO3/GPIO2

spi pin: SCLK/MOSI/MISO/CS GPIO11/GPIO10/GPIO9/GPIO8

uart pin: TX/RX GPIO14/GPIO15

gpio pin: INT GPIO17

reset pin: RESET GPIO26

### 2. install

#### 2.1 install info

```shell
sudo apt-get install libgpiod-dev

make
```

### 3. mfrc522

#### 3.1 command Instruction

​           mfrc522 is a basic command which can test all mfrc522 driver function:

​           -i          show mfrc522 chip and driver information.

​           -h        show mfrc522 help.

​           -p        show mfrc522 pin connections of the current board.

​           -t  (reg (-spi | -uart | -iic <addr>)  | mifare (-spi | -uart | -iic <addr>))

​           -t  reg (-spi | -uart | -iic <addr>)        run mfrc522 register test. addr is the iic address.

​           -t mifare (-spi | -uart | -iic <addr>)        run mfrc522 mifare test. addr is the iic address.

​           -c (mifare (-spi | -uart | -iic <addr>)  <data> | crc (-spi | -uart | -iic <addr>)  <data> | random (-spi | -uart | -iic <addr>))

​           -c mifare (-spi | -uart | -iic <addr>)  <data>        run mfrc522 mifare function.addr is the iic address, data is the send data and data is hexadecimal.

​           -c crc (-spi | -uart | -iic <addr>)  <data>        run mfrc522 crc function.addr is the iic address, data is the send data and data is hexadecimal.

​           -c random (-spi | -uart | -iic <addr>)         run mfrc522 random function.addr is the iic address.

#### 3.2 command example

```shell
./mfrc522 -i

mfrc522: chip is NXP MFRC522.
mfrc522: manufacturer is NXP.
mfrc522: interface is IIC SPI UART.
mfrc522: driver version is 1.0.
mfrc522: min supply voltage is 2.5V.
mfrc522: max supply voltage is 3.6V.
mfrc522: max current is 100.00mA.
mfrc522: max temperature is 85.0C.
mfrc522: min temperature is -25.0C.
```

```shell
./mfrc522 -p

mfrc522: SPI interface SCK connected to GPIO11(BCM).
mfrc522: SPI interface MISO connected to GPIO9(BCM).
mfrc522: SPI interface MOSI connected to GPIO10(BCM).
mfrc522: SPI interface CS connected to GPIO8(BCM).
mfrc522: IIC interface SCL connected to GPIO3(BCM).
mfrc522: IIC interface SDA connected to GPIO2(BCM).
mfrc522: UART interface TX connected to GPIO14(BCM).
mfrc522: UART interface RX connected to GPIO15(BCM).
mfrc522: INT connected to GPIO17(BCM).
mfrc522: RESET connected to GPIO26(BCM).
```

```shell
./mfrc522 -t reg -spi

mfrc522: chip is NXP MFRC522.
mfrc522: manufacturer is NXP.
mfrc522: interface is IIC SPI UART.
mfrc522: driver version is 1.0.
mfrc522: min supply voltage is 2.5V.
mfrc522: max supply voltage is 3.6V.
mfrc522: max current is 100.00mA.
mfrc522: max temperature is 85.0C.
mfrc522: min temperature is -25.0C.
mfrc522: start register test.
mfrc522: mfrc522_set_addr_pin/mfrc522_get_addr_pin test.
mfrc522: set addr 0x8D.
mfrc522: check addr pin ok.
mfrc522: mfrc522_set_interface/mfrc522_get_interface test.
mfrc522: set interface iic.
mfrc522: check interface ok.
mfrc522: set interface spi.
mfrc522: check interface ok.
mfrc522: set interface uart.
mfrc522: check interface ok.
mfrc522: mfrc522_set_receiver_analog/mfrc522_get_receiver_analog test.
mfrc522: set receiver analog enable.
mfrc522: check receiver analog ok.
mfrc522: set receiver analog disable.
mfrc522: check receiver analog ok.
mfrc522: mfrc522_set_power_down/mfrc522_get_power_down test.
mfrc522: set power down enable.
mfrc522: check power down ok.
mfrc522: set power down disable.
mfrc522: check power down ok.
mfrc522: mfrc522_set_interrupt1/mfrc522_get_interrupt1 test.
mfrc522: set tx interrupt1 enable.
mfrc522: check interrupt1 ok.
mfrc522: set tx interrupt1 disable.
mfrc522: check interrupt1 ok.
mfrc522: set rx interrupt1 enable.
mfrc522: check interrupt1 ok.
mfrc522: set rx interrupt1 disable.
mfrc522: check interrupt1 ok.
mfrc522: set idle interrupt1 enable.
mfrc522: check interrupt1 ok.
mfrc522: set idle interrupt1 disable.
mfrc522: check interrupt1 ok.
mfrc522: set hi alert interrupt1 enable.
mfrc522: check interrupt1 ok.
mfrc522: set hi alert interrupt1 disable.
mfrc522: check interrupt1 ok.
mfrc522: set lo alert interrupt1 enable.
mfrc522: check interrupt1 ok.
mfrc522: set lo alert interrupt1 disable.
mfrc522: check interrupt1 ok.
mfrc522: set err interrupt1 enable.
mfrc522: check interrupt1 ok.
mfrc522: set err interrupt1 disable.
mfrc522: check interrupt1 ok.
mfrc522: set timer interrupt1 enable.
mfrc522: check interrupt1 ok.
mfrc522: set timer interrupt1 disable.
mfrc522: check interrupt1 ok.
mfrc522: mfrc522_set_interrupt1_pin_invert/mfrc522_get_interrupt1_pin_invert test.
mfrc522: set interrupt1 pin invert enable.
mfrc522: check invert ok.
mfrc522: set interrupt1 pin invert disable.
mfrc522: check invert ok.
mfrc522: mfrc522_set_interrupt1_trigger test.
mfrc522: set interrupt1 trigger set.
mfrc522: check interrupt1 trigger ok.
mfrc522: set interrupt1 trigger cleared.
mfrc522: check interrupt1 trigger ok.
mfrc522: mfrc522_set_interrupt2/mfrc522_get_interrupt2 test.
mfrc522: set mafin act interrupt2 enable.
mfrc522: check interrupt2 ok.
mfrc522: set mafin act interrupt2 disable.
mfrc522: check interrupt2 ok.
mfrc522: set crc interrupt2 enable.
mfrc522: check interrupt2 ok.
mfrc522: set crc interrupt2 disable.
mfrc522: check interrupt2 ok.
mfrc522: mfrc522_set_interrupt_pin_type/mfrc522_get_interrupt_pin_type test.
mfrc522: set interrupt pin type standard cmos.
mfrc522: check interrupt pin type ok.
mfrc522: set interrupt pin type open drain.
mfrc522: check interrupt pin type ok.
mfrc522: mfrc522_set_interrupt1_mark test.
mfrc522: set interrupt1 mark set.
mfrc522: check interrupt1 mark ok.
mfrc522: set interrupt1 mark cleared.
mfrc522: check interrupt1 mark ok.
mfrc522: mfrc522_set_interrupt2_mark test.
mfrc522: set interrupt2 mark set.
mfrc522: check interrupt2 mark ok.
mfrc522: set interrupt2 mark cleared.
mfrc522: check interrupt2 mark ok.
mfrc522: mfrc522_get_interrupt1_status test.
mfrc522: interrupt1 status is 0x04.
mfrc522: mfrc522_get_interrupt2_status test.
mfrc522: interrupt2 status is 0x00.
mfrc522: mfrc522_get_error test.
mfrc522: erro is 0x00.
mfrc522: mfrc522_get_status1 test.
mfrc522: status1 is 0x21.
mfrc522: mfrc522_get_status2 test.
mfrc522: status2 is 0x00.
mfrc522: mfrc522_get_modem_state test.
mfrc522: modem state is 0x00.
mfrc522: mfrc522_set_mifare_crypto1_on/mfrc522_get_mifare_crypto1_on test.
mfrc522: set mifare crypto1 on enable.
mfrc522: check mifare crypto1 on ok.
mfrc522: set mifare crypto1 on disable.
mfrc522: check mifare crypto1 on ok.
mfrc522: mfrc522_set_force_iic_high_speed/mfrc522_get_force_iic_high_speed test.
mfrc522: set force iic high speed enable.
mfrc522: check force iic high speed ok.
mfrc522: set force iic high speed disable.
mfrc522: check force iic high speed ok.
mfrc522: mfrc522_set_clear_temperature_error/mfrc522_get_clear_temperature_error test.
mfrc522: set clear temperature error enable.
mfrc522: check clear temperature error enable ok.
mfrc522: set clear temperature error disable.
mfrc522: check clear temperature error enable ok.
mfrc522: mfrc522_get_fifo_level test.
mfrc522: fifo level is 0x00.
mfrc522: mfrc522_flush_fifo test.
mfrc522: check flush fifo ok.
mfrc522: mfrc522_set_water_level/mfrc522_get_water_level test.
mfrc522: set water level 0x01.
mfrc522: check water level ok.
mfrc522: mfrc522_start_timer test.
mfrc522: check start timer ok.
mfrc522: mfrc522_stop_timer test.
mfrc522: check stop timer ok.
mfrc522: mfrc522_get_rx_last_bits test.
mfrc522: rx last bits is 0x00.
mfrc522: mfrc522_start_send test.
mfrc522: check start send ok.
mfrc522: mfrc522_stop_send test.
mfrc522: check stop send ok.
mfrc522: mfrc522_set_tx_last_bits/mfrc522_get_tx_last_bits test.
mfrc522: set tx last bits 0x07.
mfrc522: check tx last bits ok.
mfrc522: mfrc522_set_rx_align/mfrc522_get_rx_align test.
mfrc522: set rx align 0.
mfrc522: check rx align ok.
mfrc522: set rx align 1.
mfrc522: check rx align ok.
mfrc522: set rx align 7.
mfrc522: check rx align ok.
mfrc522: mfrc522_set_value_clear_after_coll/mfrc522_get_value_clear_after_coll test.
mfrc522: set value clear after coll enable.
mfrc522: check value clear after coll ok.
mfrc522: set value clear after coll disable.
mfrc522: check value clear after coll ok.
mfrc522: mfrc522_get_collision_position_not_valid test.
mfrc522: collision position not valid is true.
mfrc522: mfrc522_get_collision_position_not_valid test.
mfrc522: collision position is 0x00.
mfrc522: mfrc522_set_crc_msb_first/mfrc522_get_crc_msb_first test.
mfrc522: set crc msb first enable.
mfrc522: check get crc msb first ok.
mfrc522: set crc msb first disable.
mfrc522: check get crc msb first ok.
mfrc522: mfrc522_set_tx_wait_rf/mfrc522_get_tx_wait_rf test.
mfrc522: set tx wait rf enable .
mfrc522: check tx wait rf ok.
mfrc522: set tx wait rf disable .
mfrc522: check tx wait rf ok.
mfrc522: mfrc522_set_mfin_polarity/mfrc522_get_mfin_polarity test.
mfrc522: set mfin polarity low.
mfrc522: check mfin polarity ok.
mfrc522: set mfin polarity high.
mfrc522: check mfin polarity ok.
mfrc522: mfrc522_set_crc_preset/mfrc522_get_crc_preset test.
mfrc522: set crc preset 0000.
mfrc522: check crc preset ok.
mfrc522: set crc preset 6363.
mfrc522: check crc preset ok.
mfrc522: set crc preset A671.
mfrc522: check crc preset ok.
mfrc522: set crc preset FFFF.
mfrc522: check crc preset ok.
mfrc522: mfrc522_set_tx_crc_generation/mfrc522_get_tx_crc_generation test.
mfrc522: set tx crc generation enable.
mfrc522: check tx crc generation ok.
mfrc522: set tx crc generation disable.
mfrc522: check tx crc generation ok.
mfrc522: mfrc522_set_tx_speed/mfrc522_get_tx_speed test.
mfrc522: set tx speed 106 kBd.
mfrc522: check tx speed ok.
mfrc522: set tx speed 212 kBd.
mfrc522: check tx speed ok.
mfrc522: set tx speed 424 kBd.
mfrc522: check tx speed ok.
mfrc522: set tx speed 848 kBd.
mfrc522: check tx speed ok.
mfrc522: mfrc522_set_modulation_invert/mfrc522_get_modulation_invert test.
mfrc522: set modulation invert enable.
mfrc522: check modulation invert ok.
mfrc522: set modulation invert disable.
mfrc522: check modulation invert ok.
mfrc522: mfrc522_set_rx_crc_generation/mfrc522_get_rx_crc_generation test.
mfrc522: set rx crc generation enable.
mfrc522: check rx crc generation ok.
mfrc522: set rx crc generation disable.
mfrc522: check rx crc generation ok.
mfrc522: mfrc522_set_rx_speed/mfrc522_get_rx_speed test.
mfrc522: set rx speed 106 kBd.
mfrc522: check rx speed ok.
mfrc522: set rx speed 212 kBd.
mfrc522: check rx speed ok.
mfrc522: set rx speed 424 kBd.
mfrc522: check rx speed ok.
mfrc522: set rx speed 848 kBd.
mfrc522: check rx speed ok.
mfrc522: mfrc522_set_rx_no_error/mfrc522_get_rx_no_error test.
mfrc522: set rx no error enable.
mfrc522: check rx no error ok.
mfrc522: set rx no error disable.
mfrc522: check rx no error ok.
mfrc522: mfrc522_set_rx_multiple/mfrc522_get_rx_multiple test.
mfrc522: set rx multiple enable.
mfrc522: check rx multiple ok.
mfrc522: set rx multiple disable.
mfrc522: check rx multiple ok.
mfrc522: mfrc522_set_antenna_driver/mfrc522_get_antenna_driver test.
mfrc522: set antenna driver inv tx2 rf on enable.
mfrc522: check antenna driver ok.
mfrc522: set antenna driver inv tx2 rf on disable.
mfrc522: check antenna driver ok.
mfrc522: set antenna driver inv tx1 rf on enable.
mfrc522: check antenna driver ok.
mfrc522: set antenna driver inv tx1 rf on disable.
mfrc522: check antenna driver ok.
mfrc522: set antenna driver inv tx2 rf off enable.
mfrc522: check antenna driver ok.
mfrc522: set antenna driver inv tx2 rf off disable.
mfrc522: check antenna driver ok.
mfrc522: set antenna driver inv tx1 rf off enable.
mfrc522: check antenna driver ok.
mfrc522: set antenna driver inv tx1 rf off disable.
mfrc522: check antenna driver ok.
mfrc522: set antenna driver tx2 cw enable.
mfrc522: check antenna driver ok.
mfrc522: set antenna driver tx2 cw disable.
mfrc522: check antenna driver ok.
mfrc522: set antenna driver tx2 rf enable.
mfrc522: check antenna driver ok.
mfrc522: set antenna driver tx2 rf disable.
mfrc522: check antenna driver ok.
mfrc522: set antenna driver tx1 rf enable.
mfrc522: check antenna driver ok.
mfrc522: set antenna driver tx1 rf disable.
mfrc522: check antenna driver ok.
mfrc522: mfrc522_set_force_100_ask/mfrc522_get_force_100_ask test.
mfrc522: set force 100 ask enable.
mfrc522: check force 100 ask ok.
mfrc522: set force 100 ask disable.
mfrc522: check force 100 ask ok.
mfrc522: mfrc522_set_tx_input/mfrc522_get_tx_input test.
mfrc522: set tx input 3 state.
mfrc522: check tx input ok.
mfrc522: set tx input internal encoder.
mfrc522: check tx input ok.
mfrc522: set tx input mfin pin.
mfrc522: check tx input ok.
mfrc522: set tx input control.
mfrc522: check tx input ok.
mfrc522: mfrc522_set_mfout_input/mfrc522_get_mfout_input test.
mfrc522: set mfout input 3 state.
mfrc522: check mfout input ok.
mfrc522: set mfout input low.
mfrc522: check mfout input ok.
mfrc522: set mfout input high.
mfrc522: check mfout input ok.
mfrc522: set mfout input test.
mfrc522: check mfout input ok.
mfrc522: set mfout input internal encoder.
mfrc522: check mfout input ok.
mfrc522: set mfout input transmitted.
mfrc522: check mfout input ok.
mfrc522: set mfout input received.
mfrc522: check mfout input ok.
mfrc522: mfrc522_set_contactless_uart_input/mfrc522_get_contactless_uart_input test.
mfrc522: set contactless uart input constant low.
mfrc522: check contactless uart input ok.
mfrc522: set contactless uart input mfin pin.
mfrc522: check contactless uart input ok.
mfrc522: set contactless uart input internal analog module.
mfrc522: check contactless uart input ok.
mfrc522: set contactless uart input nrz.
mfrc522: check contactless uart input ok.
mfrc522: mfrc522_set_rx_wait/mfrc522_get_rx_wait test.
mfrc522: set rx wait 0x1E.
mfrc522: check rx wait ok.
mfrc522: mfrc522_set_min_level/mfrc522_get_min_level test.
mfrc522: set min level 0x02.
mfrc522: check min level ok.
mfrc522: mfrc522_set_collision_level/mfrc522_get_collision_level test.
mfrc522: set collision level 0x06.
mfrc522: check collision level ok.
mfrc522: mfrc522_set_channel_reception/mfrc522_get_channel_reception test.
mfrc522: set channel reception stronger channel.
mfrc522: check channel reception ok.
mfrc522: set channel reception stronger channel and freezes the selected channel.
mfrc522: check channel reception ok.
mfrc522: mfrc522_set_fix_iq/mfrc522_get_fix_iq test.
mfrc522: set fix iq enable.
mfrc522: check fix iq ok.
mfrc522: set fix iq disable.
mfrc522: check fix iq ok.
mfrc522: mfrc522_set_timer_prescal_even/mfrc522_get_timer_prescal_even test.
mfrc522: set timer prescal even enable.
mfrc522: check timer prescal even ok.
mfrc522: set timer prescal even disable.
mfrc522: check timer prescal even ok.
mfrc522: mfrc522_set_timer_constant_reception/mfrc522_get_timer_constant_reception test.
mfrc522: set timer constant reception 0x02.
mfrc522: check timer constant reception ok.
mfrc522: mfrc522_set_timer_constant_sync/mfrc522_get_timer_constant_sync test.
mfrc522: set timer constant sync 0x01.
mfrc522: check timer constant sync ok.
mfrc522: mfrc522_set_tx_wait/mfrc522_get_tx_wait test.
mfrc522: set tx wait 0x02.
mfrc522: check tx wait ok.
mfrc522: mfrc522_set_parity_disable/mfrc522_get_parity_disable test.
mfrc522: set parity disable enable.
mfrc522: check parity disable ok.
mfrc522: set parity disable disable.
mfrc522: check parity disable ok.
mfrc522: mfrc522_set_serial_speed/mfrc522_get_serial_speed test.
mfrc522: set serial speed t0 0x03.
mfrc522: set serial speed t1 0x05.
mfrc522: check serial speed t0 ok.
mfrc522: check serial speed t1 ok.
mfrc522: mfrc522_get_crc test.
mfrc522: crc is 0xFFFF.
mfrc522: mfrc522_set_modulation_width/mfrc522_get_modulation_width test.
mfrc522: set modulation width 0x48.
mfrc522: check modulation width ok.
mfrc522: mfrc522_set_rx_gain/mfrc522_get_rx_gain test.
mfrc522: set rx gain 18 db.
mfrc522: check rx gain ok.
mfrc522: set rx gain 23 db.
mfrc522: check rx gain ok.
mfrc522: set rx gain 33 db.
mfrc522: check rx gain ok.
mfrc522: set rx gain 38 db.
mfrc522: check rx gain ok.
mfrc522: set rx gain 43 db.
mfrc522: check rx gain ok.
mfrc522: set rx gain 48 db.
mfrc522: check rx gain ok.
mfrc522: mfrc522_set_cwgsn/mfrc522_get_cwgsn test.
mfrc522: set cwgsn 0x02.
mfrc522: check cwgsn ok.
mfrc522: mfrc522_set_modgsn/mfrc522_get_modgsn test.
mfrc522: set modgsn 0x08.
mfrc522: check modgsn ok.
mfrc522: mfrc522_set_cwgsp/mfrc522_get_cwgsp test.
mfrc522: set cwgsp 0x08.
mfrc522: check cwgsp ok.
mfrc522: mfrc522_set_modgsp/mfrc522_get_modgsp test.
mfrc522: set modgsp 0x3B.
mfrc522: check modgsp ok.
mfrc522: mfrc522_set_timer_auto/mfrc522_get_timer_auto test.
mfrc522: set timer auto enable.
mfrc522: check timer auto ok.
mfrc522: set timer auto disable.
mfrc522: check timer auto ok.
mfrc522: mfrc522_set_timer_gated_mode/mfrc522_get_timer_gated_mode test.
mfrc522: set timer gated mode none.
mfrc522: check timer gated mode ok.
mfrc522: set timer gated mode mfin.
mfrc522: check timer gated mode ok.
mfrc522: set timer gated mode aux1.
mfrc522: check timer gated mode ok.
mfrc522: mfrc522_set_timer_auto_restart/mfrc522_get_timer_auto_restart test.
mfrc522: set timer auto restart enable.
mfrc522: check timer auto restart ok.
mfrc522: set timer auto restart disable.
mfrc522: check timer auto restart ok.
mfrc522: mfrc522_set_timer_prescaler/mfrc522_get_timer_prescaler test.
mfrc522: set timer prescaler 0x09A2.
mfrc522: check timer prescaler ok.
mfrc522: mfrc522_set_timer_reload/mfrc522_get_timer_reload test.
mfrc522: set timer reload 0xED53.
mfrc522: check timer reload ok.
mfrc522: mfrc522_get_timer_counter test.
mfrc522: check timer reload 0x0000.
mfrc522: mfrc522_set_fifo_data/mfrc522_get_fifo_data test.
mfrc522: check fifo data ok.
mfrc522: mfrc522_set_test_bus_signal_1/mfrc522_get_test_bus_signal_1 test.
mfrc522: set test bus signal 1 0x04.
mfrc522: check test bus signal 1 ok.
mfrc522: mfrc522_set_test_bus_signal_2/mfrc522_get_test_bus_signal_2 test.
mfrc522: set test bus signal 2 0x1E.
mfrc522: check test bus signal 2 ok.
mfrc522: mfrc522_set_test_bus_flip/mfrc522_get_test_bus_flip test.
mfrc522: set test bus flip enable.
mfrc522: check test bus flip ok.
mfrc522: set test bus flip disable.
mfrc522: check test bus flip ok.
mfrc522: mfrc522_set_test_prbs9/mfrc522_get_test_prbs9 test.
mfrc522: set test prbs9 enable.
mfrc522: check test prbs9 ok.
mfrc522: set test prbs9 disable.
mfrc522: check test prbs9 ok.
mfrc522: mfrc522_set_test_prbs15/mfrc522_get_test_prbs15 test.
mfrc522: set test prbs15 enable.
mfrc522: check test prbs15 ok.
mfrc522: set test prbs15 disable.
mfrc522: check test prbs15 ok.
mfrc522: mfrc522_set_test_rs232_line/mfrc522_get_test_rs232_line test.
mfrc522: set test rs232 line enable.
mfrc522: check test rs232 line ok.
mfrc522: set test rs232 line disable.
mfrc522: check test rs232 line ok.
mfrc522: mfrc522_set_test_pin_enable/mfrc522_get_test_pin_enable test.
mfrc522: set test pin enable 0x1B.
mfrc522: check test pin enable ok.
mfrc522: mfrc522_set_test_port_io/mfrc522_get_test_port_io test.
mfrc522: set test port io enable.
mfrc522: check test port io ok.
mfrc522: set test port io disable.
mfrc522: check test port io ok.
mfrc522: mfrc522_set_test_pin_value/mfrc522_get_test_pin_value test.
mfrc522: set test pin value 0x11.
mfrc522: check test pin value ok.
mfrc522: mfrc522_get_test_bus test.
mfrc522: get test bus 0x00.
mfrc522: mfrc522_set_test_amp_rcv/mfrc522_get_test_amp_rcv test.
mfrc522: set test amp rcv enable.
mfrc522: check test amp rcv ok.
mfrc522: set test amp rcv disable.
mfrc522: check test amp rcv ok.
mfrc522: mfrc522_set_self_test/mfrc522_get_self_test test.
mfrc522: set self test 0x00.
mfrc522: check self test ok.
mfrc522: mfrc522_get_version test.
mfrc522: id is 0x09, version is 0x02.
mfrc522: mfrc522_set_test_analog_control_aux_1/mfrc522_get_test_analog_control_aux_1 test.
mfrc522: set test analog control aux 1 3 state.
mfrc522: check test analog control aux 1 ok.
mfrc522: set test analog control aux 1 output.
mfrc522: check test analog control aux 1 ok.
mfrc522: set test analog control aux 1 test signal corr1.
mfrc522: check test analog control aux 1 ok.
mfrc522: set test analog control aux 1 dac test signal min level.
mfrc522: check test analog control aux 1 ok.
mfrc522: set test analog control aux 1 dac test signal adc i.
mfrc522: check test analog control aux 1 ok.
mfrc522: set test analog control aux 1 dac test signal adc q.
mfrc522: check test analog control aux 1 ok.
mfrc522: set test analog control aux 1 test signal for production.
mfrc522: check test analog control aux 1 ok.
mfrc522: set test analog control aux 1 high.
mfrc522: check test analog control aux 1 ok.
mfrc522: set test analog control aux 1 low.
mfrc522: check test analog control aux 1 ok.
mfrc522: set test analog control aux 1 tx active.
mfrc522: check test analog control aux 1 ok.
mfrc522: set test analog control aux 1 rx active.
mfrc522: check test analog control aux 1 ok.
mfrc522: set test analog control aux 1 subcarrier detected.
mfrc522: check test analog control aux 1 ok.
mfrc522: set test analog control aux 1 defined bit.
mfrc522: check test analog control aux 1 ok.
mfrc522: mfrc522_set_test_analog_control_aux_2/mfrc522_get_test_analog_control_aux_2 test.
mfrc522: set test analog control aux 2 3 state.
mfrc522: check test analog control aux 2 ok.
mfrc522: set test analog control aux 2 output.
mfrc522: check test analog control aux 2 ok.
mfrc522: set test analog control aux 2 test signal corr1.
mfrc522: check test analog control aux 2 ok.
mfrc522: set test analog control aux 2 dac test signal min level.
mfrc522: check test analog control aux 2 ok.
mfrc522: set test analog control aux 2 dac test signal adc i.
mfrc522: check test analog control aux 2 ok.
mfrc522: set test analog control aux 2 dac test signal adc q.
mfrc522: check test analog control aux 2 ok.
mfrc522: set test analog control aux 2 test signal for production.
mfrc522: check test analog control aux 2 ok.
mfrc522: set test analog control aux 2 high.
mfrc522: check test analog control aux 2 ok.
mfrc522: set test analog control aux 2 low.
mfrc522: check test analog control aux 2 ok.
mfrc522: set test analog control aux 2 tx active.
mfrc522: check test analog control aux 2 ok.
mfrc522: set test analog control aux 2 rx active.
mfrc522: check test analog control aux 2 ok.
mfrc522: set test analog control aux 2 subcarrier detected.
mfrc522: check test analog control aux 2 ok.
mfrc522: set test analog control aux 2 defined bit.
mfrc522: check test analog control aux 2 ok.
mfrc522: mfrc522_set_test_dac_1/mfrc522_get_test_dac_1 test.
mfrc522: set test dac 1 0x1F.
mfrc522: check test dac 1 ok.
mfrc522: mfrc522_set_test_dac_2/mfrc522_get_test_dac_2 test.
mfrc522: set test dac 2 0x2A.
mfrc522: check test dac 2 ok.
mfrc522: mfrc522_get_test_adc test.
mfrc522: test adc i is 0x08 adc q is 0x08.
mfrc522: finish register test.
```

```shell
./mfrc522 -t mifare -spi

mfrc522: chip is NXP MFRC522.
mfrc522: manufacturer is NXP.
mfrc522: interface is IIC SPI UART.
mfrc522: driver version is 1.0.
mfrc522: min supply voltage is 2.5V.
mfrc522: max supply voltage is 3.6V.
mfrc522: max current is 100.00mA.
mfrc522: max temperature is 85.0C.
mfrc522: min temperature is -25.0C.
mfrc522: start mifare test.
mfrc522: irq lo alert.
mfrc522: irq idle.
mfrc522: mifare random test.
mfrc522: irq lo alert.
mfrc522: irq idle.
mfrc522: irq lo alert.
mfrc522: irq idle.
0xC9 0x58 0x77 0xFF 0xCA 0x41 0xC3 0x01 0xFF 0x81 0x9A 0x1F 0x60 0x93 0xA9 0x02 0x01 0x21 0x78 0x27 0x83 0x10 0x40 0x48 0xF9 
mfrc522: mifare crc test.
mfrc522: irq lo alert.
mfrc522: irq crc.
mfrc522: mfrc522 crc is 0x0564 and checked ok.
mfrc522: mifare find card test.
mfrc522: irq lo alert.
mfrc522: irq rx.
mfrc522: irq tx.
mfrc522: find mifare S50.
mfrc522: mifare anticoll test.
mfrc522: irq lo alert.
mfrc522: irq rx.
mfrc522: irq tx.
mfrc522: id is 0xF7 0x11 0xC3 0xB4.
mfrc522: finish mifare test.
```

```shell
./mfrc522 -c mifare -spi 26

0x04 0x00 0x33 0x33 0x33 0x33 0x33 0x33 0x33 0x33 0x33 0x33 0x33 0x33 0x33 0x33 0x66 0x24 0x00 0x08 0x00 0x00 0x00 0x81 0x00 
```

```shell
./mfrc522 -c crc -spi 0123456

0123456 crc is 0x4090.
```

```shell
./mfrc522 -c random -spi 

0xC9 0x58 0xE1 0x67 0x84 0x41 0xC3 0x01 0xDB 0x56 0x2D 0x0D 0xB8 0xA9 0x02 0x01 0x21 0x78 0x27 0x83 0x10 0x40 0x48 0xD5 0x42 
```

```shell
./mfrc522 -h

mfrc522 -i
	show mfrc522 chip and driver information.
mfrc522 -h
	show mfrc522 help.
mfrc522 -p
	show mfrc522 pin connections of the current board.
mfrc522 -t reg (-spi | -uart | -iic <addr>)
	run mfrc522 register test.addr is the iic address.
mfrc522 -t mifare (-spi | -uart | -iic <addr>)
	run mfrc522 mifare test.addr is the iic address.
mfrc522 -c mifare (-spi | -uart | -iic <addr>) <data>
	run mfrc522 mifare function.addr is the iic address, data is the send data and data is hexadecimal.
mfrc522 -c crc (-spi | -uart | -iic <addr>) <data>
	run mfrc522 crc function.addr is the iic address, data is the send data and data is hexadecimal.
mfrc522 -c random (-spi | -uart | -iic <addr>)
	run mfrc522 random function.addr is the iic address.
```