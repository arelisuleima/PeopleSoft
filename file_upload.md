>  File upload with PUSH BOTTOM LINK in peoplecode 😶‍🌫️

```PeopleCode
 &ATTACHSYSFILENAME = " ";
&ATTACHUSERFILE = " ";


&retcode = AddAttachment(URL.YOUR_URL_NAME, &ATTACHSYSFILENAME, "", &ATTACHUSERFILE, 0);

If &retcode <> 0 Then
   /*GetRecord().FILE_NAME.SetDefault();*/
   SetDefault(RUN_CONTROL_TABLE_NAME.FILENAME);
   Error MsgGet(25000, 6, "Missing Error");
Else
   RUN_CONTROL_TABLE_NAME.FILENAME.Value = &ATTACHUSERFILE;
End-If;
```
