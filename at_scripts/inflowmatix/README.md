# Inflowmatix Scripts for u-blox m-center

### Typical Usage

Preparation:
1. Connect the R412M modem via USB cable to the Windows laptop
2. Start m-center
3. Power on the modem and then select the AT and trace COM port
   - Can use the button on the EVK-R4 to trigger power on
4. Power off the modem
   - Send the `AT+CPWROFF` command

Test process:
1. Power on the modem
   - Can use the button on the EVK-R4 to trigger power on
2. Run the m-center script [inflowmatix_sara_r412_configure_phase_1.atl](inflowmatix_sara_r412_configure_phase_1.atl)
   - If the AT COM port was disconnected then it may be necessary to press the `Connect` button
3. Run the m-center script [inflowmatix_sara_r412_configure_phase_2.atl](inflowmatix_sara_r412_configure_phase_2.atl)
   - If the AT COM port gets disconnected then it may be necessary to press the `Connect` button
4. Run the m-center script [inflowmatix_sara_r412_configure_phase_3.atl](inflowmatix_sara_r412_configure_phase_3.atl)
   - If the AT COM port gets disconnected then it may be necessary to press the `Connect` button
5. Run the m-center script [inflowmatix_sara_r412_network_registration.atl](inflowmatix_sara_r412_network_registration.atl)
   - If the AT COM port gets disconnected then it may be necessary to press the `Connect` button
6. Wait for the script to finish
7. Run the m-center script [debug_saraR41_basic.atl](../debug-ability/debug_saraR41_basic.atl)
8. Wait for a few minutes after the script has finished
    - Some URCs will be periodically reported
9. Run the m-center script [inflowmatix_undo_debug_saraR41_basic.atl](inflowmatix_undo_debug_saraR41_basic.atl)
    - This disables some URCs that were enabled by the m-center script [debug_saraR41_basic.atl](../debug-ability/debug_saraR41_basic.atl)
10. Run the m-center script [inflowmatix_sara_r412_debug_additional.atl](inflowmatix_sara_r412_debug_additional.atl)
    - This runs some additional checks not included in the m-center script [debug_saraR41_basic.atl](../debug-ability/debug_saraR41_basic.atl)
11. Power off the modem
    - Send the `AT+CPWROFF` command
12. Stop the m-center trace
    - This was started in the m-center script [inflowmatix_sara_r412_network_registration.atl](inflowmatix_sara_r412_network_registration.atl)
13. Locate and save both the m-center AT log file and the trace file
