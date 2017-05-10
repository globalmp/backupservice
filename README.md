# backupservice
<p>Making backup all files and dirs in folder. Backup the database. Merging all backups and sending to email address</p>

<h2>Data Base setting</h2>

<p><code>define(DBHOST, 'localhost');</code> - Host name or IP-adress database (mysql) server</p>
<p><code>define(DBUSER, 'root');</code> - database user name</p>
<p><code>define(DBPASSWD, '');</code> - database password</p>
<p><code>define(DBNAME, '');</code> - database name</p>

<h2>SMTP (Email) sending setting</h2>

<p><code>define(SEND_EMAIL, 'info@example.com');</code> - Email from sending</p>
<p><code>define(SMTP_SERVER, 'smtp.example.com');</code> - Server to the sending</p>
<p><code>define(SMTP_PORT, '465');</code> - Port of server</p>
<p><code>define(SMTP_USER, 'info@example.com');</code> - User for auth on smtp server</p>
<p><code>define(SMTP_PASSWD, '');</code> - Password of user to auth on smtp server</p>
<p><code>define(SMTP_SECURE, 'ssl');</code> - Type of secure. tls or ssl</p>

<h2>Date time formats</h2>

<p><code>define(DATETIMEFORMAT, 'd/m/Y H:i:s');</code> - data time format to inner data</p>
<p><code>define(DATETIMEFORMATFORFILE, 'd-m-y-h-i-s');</code> - date time format to outer (in file name). <b>optional</b></p>

<h2>Methods</h2>

<table>
<tr>
<td width="20%">
<b>filename( data )</b>
</td>
<td width="20%">string</td>
<td>Backup archive file name. Add before time data. If the last used.</td>
</tr>

<tr>
<td>
<b>db()</b>
</td>
<td>void</td>
<td>If you create and database backup. Necessary use this method before zip()  <b>optional</b></td>
</tr>

<tr>
<td>
<b>addTime()</b>
</td>
<td>void</td>
<td>Add time data to file name. Use <i>DATETIMEFORMATFORFILE</i> <b>optional</b></td>
</tr>

<tr>
<td>
<b>sendTo( data )</b>
</td>
<td>string or array</td>
<td>Email adresses to the send backup. <b>optional</b></td>
</tr>

<tr>
<td>
<b>findTo( data )</b>
</td>
<td>string</td>
<td>Folder to extract files and dirs for backup. Search data making only this folder. <b>optional</b></td>
</tr>

<tr>
<td>
<b>saveTo( data )</b>
</td>
<td>string</td>
<td>Folder to the save backup ziparchive. Permission (chmod) 0777 <b>optional</b></td>
</tr>

<tr>
<td>
<b>zip()</b>
</td>
<td>void</td>
<td>Basic method. This method merge db backup and files backup and (if selected) sending to emails.</td>
</tr>

<tr>
<td>
<b>deleteBackup()</b>
</td>
<td>void</td>
<td>Delete the backup archive. <b>ATTENTION!</b> use this method only after call method zip()</td>
</tr>



</table>

<h2>Example</h2>
<p><code>(new backup)->filename( "SlavaNadejdin" )->db()->addTime()->sendTo( "info@example.com" )->findTo( "" )->saveTo( "tmp" )->zip()->deleteBackup();</code></p>
