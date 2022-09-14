# WINC3400-known-issues
More info may be available via WINC3400 Harmony 3 release notes [here](https://github.com/Microchip-MPLAB-Harmony/wireless_apps_winc3400/blob/master/release_notes.md)

<table>
  <tbody>
     <tr>
        <th>No.</th>
        <th>Deliverable</th>
        <th>ID</th>
        <th>Issue / Limitation</th>
        <th>Affected Version(s)</th>
        <th>Fix Version(s)</th>
        <th>Recommendation</th>
    </tr>
    <tr>
          <td>1</td>
          <td> WINC FW, driver and PC programming tools</td>
          <td>-</td>
          <td>If WINC flash is marginally programmed, possible WINC flash corruption may occur where random flash bytes can randomly show 0 or 1 logic upon flash read.                     Symptoms are that WINC part is unable to boot, unable to start, unable to complete initialization or hang during run time</td>
          <td>
              <ul>
                  <li>A part that's running 1.2.2 FW/driver or older</li>
                  <li>A part that's upgraded to any version using 1.2.2 or older built-in OTA</li>
                  <li>A part that's upgraded to any version using 1.2.2 or older host driver SPI flash APIs</li>
                  <li>A part that's upgraded to any version using 1.2.2 or older PC tools</li>
              </ul>
          </td>
          <td>WINC 1.2.3+ FW, driver and PC tools</td>
          <td> Either of the following two actions/recommendations should be followed:
              <ul>
                  <li> WINC 1.2.3+ FW, driver and PC tools execute double programming to workaround any possible marginal programming. To protect a working WINC part or to recover a flash-corrupted WINC part, upgrade to 1.2.3+ FW and driver is needed. FW upgrade must be done using:
                    <ul>
                        <li>PC tools from 1.2.3+ release package</li>
                        <li>SPI flash APIs from 1.2.3+ host driver </li>
                    </ul>
                    Note: OTA does not protect a working part against the possible flash corruption nor it recovers a flash-corrupted part
                  </li>
                  <li>
                      Make sure that WINC VDDIO which supplies WINC flash voltage is stable all the time within the recommended operating range 2.7V - 3.6V (typical 3.3V)
                  </li>
              </ul>
          </td>
    </tr>
    <tr>
          <td>2</td>
          <td> WINC3400 FIRMWARE UPDATE PROJECT</td>
          <td>-</td>
          <td>Failure to use the board-specific XO offset stored in efuse when calculating lookup tables during image creation/flashing.This may result in sub-optimal RF performance.</td>
          <td>
              <ul>
                  <li>FW Version 1.4.4</li>
              </ul>
          </td>
          <td>FW Version 1.4.4</td>
          <td> The release zip <a href="https://github.com/MicrochipTech/WINC-Releases/blob/master/WINC3400/1_4_4/WINC3400_FIRMWARE_UPDATE_PROJECT.7z">WINC3400 FIRMWARE UPDATE PROJECT</a> is updated with script "update_pll_table.bat" which will handle the extraction of XO offset from efuse, and ensure the value is used correctly during image creation.
          </td>
    </tr>
  </tbody>
</table>
