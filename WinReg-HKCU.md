# Windows Registry Entries in the Current User Hive

Example with Adobe Reader DC

- HKCU\Software\Adobe\Acrobat Reader\DC\Originals
    - bAllowOpenFile  REG_DWORD   0
      Disallow Opening of Non-PDF File Attachments with external applications (Allow Value=1)
      The Checkbox in the Gui Settings under Trust Manager/PDF File Attachment is cleared.

    - bSecureOpenFile REG_DWORD   1
      Disable "Launch Command",  Activate Value=0
      The Checkbox in the Gui Settings under Trust Manager/PDF File Attachment is greyed out.

    Links:
    - https://www.symantec.com/connect/blogs/how-disable-pdf-embedded-executable-execution-adobe-reader-pro
    - https://www.heise.de/security/meldung/Offizieller-Workaround-von-Adobe-fuer-PDF-Luecke-971836.html (German)
    - https://www.secuvera.de/blog/registry-patch-fuer-acrobat-reader-und-adobe-acrobat/

- HKCU\Software\Adobe\Acrobat Reader\DC\TrustManager\cDefaultLaunchURLPerms
    - iURLPerms REG_DWORD 1
      Block All Internet Hyperlinks, Allow All Value=2, Ask User Value=0  
      Corresponding Radio Buttons in the Gui Settings under Trust Manager/Internet Access/Change Settings

- HKCU\Software\Adobe\Acrobat Reader\DC\JSPrefs
    - bEnableJS REG_DWORD   0
      Disable Adobe Javascript, Activate Value=1
      Gui Settings under JavasSript
    
      To enable Javascript for some directories/files define them under
      Settings - Security (Enhanced). This will create additional registry entries
      under HKCU\Software\Adobe\Acrobat Reader\DC\TrustManager\cTrustedFolders .
