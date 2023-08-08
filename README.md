# OGP Debian 12 Open Game Panel PHP 8.2
Solved Failed to open libtier0.so CSGO SERVER OGP OPEN GAME PANEL

![screen](https://github.com/007amauri/OGP/assets/19276454/94ae8110-0db7-4cc9-b7ef-cbb0999ddc76)
first locate this file copy it in my documents
**libgcc_s.so.1**

/home/amauri/.local/share/Steam/steamapps/common/SteamLinuxRuntime_sniper/sniper_platform_0.20230605.51441/files/lib/i386-linux-gnu/

**i386-linux-gnu**
then you must put in the two OGP server directory

cp '/home/amauri/Documentos/libgcc_s.so.1' /home/ogp_agent/OGP_User_Files/1/bin

cp '/home/amauri/Documentos/libgcc_s.so.1' /home/ogp_agent/OGP_User_Files/1/csgo/bin


nano '/var/www/html/modules/gamemanager/stop_server.php'

Edit file stop_server.php 3 to 18

$view->refresh("?m=gamemanager&amp;p=game_monitor&amp;home_id-mod_id-ip-port=". $home_id . "-". $mod_id . "-" . $ip . "-" . $port,18);

Edit file restart_server.php 3 to 15

nano '/var/www/html/modules/gamemanager/restart_server.php'

if ( $screen_running == 1 ) // $screen_running
{
  print("<p class='note'>".get_lang('restarting_server')."</p>");
   $view->refresh("?m=gamemanager&amp;p=restart&amp;refresh&amp;ip=$ip&amp;port=$port&amp;home_id=$home_id&amp;mod_id=$mod_id",15);
   return;
}
else
{
 print_failure("".get_lang('error_occured_remote_host').".$remote_retval");
 $view->refresh("?m=gamemanager&amp;p=game_monitor&amp;home_id-mod_id-ip-port=". $home_id . "-". $mod_id . "-" . $ip . "-" . $port,15);



