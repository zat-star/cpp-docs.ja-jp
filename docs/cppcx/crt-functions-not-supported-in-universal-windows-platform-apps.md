---
title: "ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cbfc957d-6c60-48f4-97e3-1ed8526743b4
caps.latest.revision: 15
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 15
---
# ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数
多くの C ランタイム \(CRT\) 関数はユニバーサル Windows プラットフォーム \(UWP\) アプリをビルドする時に使用できません。[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] や Win32 API を使用するなど、回避策を利用できることもあります。 しかし、回避策が利用できない場合には、CRT 関数は禁止されています。CRT 関数に相当する機能やサポートする API を UWP アプリに使用できないためです。  
  
 次の一覧には UWP アプリをビルドするときに使用できない CRT 関数と、その回避策があればそれを示しています。  
  
## サポートされない CRT 関数  
  
||||  
|-|-|-|  
|\_beep \_sleep \_seterrormode|これらの関数は以前のバージョンの CRT で廃止されています。 また、それに対応する Win32 API は UWP アプリでは使用できません。|回避策はありません。|  
|chdir \_chdrive getcwd|これらの関数は廃止されているか、またはスレッド セーフではありません。|\_chdir、\_getcwd、関連する関数を使用します。|  
|\_cgets \_cgets\_s \_cgetws \_cgetws\_s \_cprintf \_cprintf\_l \_cprintf\_p \_cprintf\_p\_l \_cprintf\_s \_cprintf\_s\_l \_cputs \_cputws \_cscanf \_cscanf\_l \_cscanf\_s \_cscanf\_s\_l \_cwait \_cwprintf \_cwprintf\_l \_cwprintf\_p \_cwprintf\_p\_l \_cwprintf\_s \_cwprintf\_s\_l \_cwscanf \_cwscanf\_l \_cwscanf\_s \_cwscanf\_s\_l \_vcprintf \_vcprintf\_l \_vcprintf\_p \_vcprintf\_p\_l \_vcprintf\_s \_vcprintf\_s\_l \_vcwprintf \_vcwprintf\_l \_vcwprintf\_p \_vcwprintf\_p\_l \_vcwprintf\_s \_vcwprintf\_s\_l \_getch \_getch\_nolock \_getche \_getche\_nolock \_getwch \_getwch\_nolock \_getwche \_getwche\_nolock \_putch \_putch\_nolock \_putwch \_putwch\_nolock \_ungetch \_ungetch\_nolock \_ungetwch \_ungetwch\_nolock \_kbhit kbhit putch cgets cprintf cputs cscanf cwait getch getche ungetch|これらの関数は、コンソールから直接読み取ったり、コンソールに直接書き込んだりするときに使用されます。 UWP アプリは GUI のみであり、コンソールをサポートしていません。|回避策はありません。|  
|getpid|これは古い関数です。|\_getpid または Win32 API `GetCurrentProcessId()` を使用します。|  
|\_getdiskfree|使用できません。|Win32 API `GetDiskFreeSpaceExW()` を使用します。|  
|\_getdrive \_getdrives|対応する API はUWP アプリでは使用できません。|回避策はありません。|  
|\_inp \_inpd \_inpw \_outp \_outpd \_outpw inp inpd inpw outp outpd outpw|ポート IO は UWP アプリではサポートされていません。|回避策はありません。|  
|\_ismbcalnum \_ismbcalnum\_l \_ismbcalpha \_ismbcalpha\_l \_ismbcdigit \_ismbcdigit\_l \_ismbcgraph \_ismbcgraph\_l \_ismbchira \_ismbchira\_l \_ismbckata \_ismbckata\_l \_ismbcl0 \_ismbcl0\_l \_ismbcl1 \_ismbcl1\_l \_ismbcl2 \_ismbcl2\_l \_ismbclegal \_ismbclegal\_l \_ismbclower \_ismbclower\_l \_ismbcprint \_ismbcprint\_l \_ismbcpunct \_ismbcpunct\_l \_ismbcspace \_ismbcspace\_l \_ismbcsymbol \_ismbcsymbol\_l \_ismbcupper \_ismbcupper\_l \_mbbtombc \_mbbtombc\_l \_mbbtype \_mbbtype\_l \_mbccpy \_mbccpy\_l \_mbccpy\_s \_mbccpy\_s\_l \_mbcjistojms \_mbcjistojms\_l \_mbcjmstojis \_mbcjmstojis\_l \_mbclen \_mbclen\_l \_mbctohira \_mbctohira\_l \_mbctokata \_mbctokata\_l \_mbctolower \_mbctolower\_l \_mbctombb \_mbctombb\_l \_mbctoupper \_mbctoupper\_l \_mbsbtype \_mbsbtype\_l \_mbscat \_mbscat\_l \_mbscat\_s \_mbscat\_s\_l \_mbschr \_mbschr\_l \_mbscmp \_mbscmp\_l \_mbscoll \_mbscoll\_l \_mbscpy \_mbscpy\_l \_mbscpy\_s \_mbscpy\_s\_l \_mbscspn \_mbscspn\_l \_mbsdec \_mbsdec\_l \_mbsicmp \_mbsicmp\_l \_mbsicoll \_mbsicoll\_l \_mbsinc \_mbsinc\_l \_mbslen \_mbslen\_l \_mbslwr \_mbslwr\_l \_mbslwr\_s \_mbslwr\_s\_l \_mbsnbcat \_mbsnbcat\_l \_mbsnbcat\_s \_mbsnbcat\_s\_l \_mbsnbcmp \_mbsnbcmp\_l \_mbsnbcnt \_mbsnbcnt\_l \_mbsnbcoll \_mbsnbcoll\_l \_mbsnbcpy \_mbsnbcpy\_l \_mbsnbcpy\_s \_mbsnbcpy\_s\_l \_mbsnbicmp \_mbsnbicmp\_l \_mbsnbicoll \_mbsnbicoll\_l \_mbsnbset \_mbsnbset\_l \_mbsnbset\_s \_mbsnbset\_s\_l \_mbsncat \_mbsncat\_l \_mbsncat\_s \_mbsncat\_s\_l \_mbsnccnt \_mbsnccnt\_l \_mbsncmp \_mbsncmp\_l \_mbsncoll \_mbsncoll\_l \_mbsncpy \_mbsncpy\_l \_mbsncpy\_s \_mbsncpy\_s\_l \_mbsnextc \_mbsnextc\_l \_mbsnicmp \_mbsnicmp\_l \_mbsnicoll \_mbsnicoll\_l \_mbsninc \_mbsninc\_l \_mbsnlen \_mbsnlen\_l \_mbsnset \_mbsnset\_l \_mbsnset\_s \_mbsnset\_s\_l \_mbspbrk \_mbspbrk\_l \_mbsrchr \_mbsrchr\_l \_mbsrev \_mbsrev\_l \_mbsset \_mbsset\_l \_mbsset\_s \_mbsset\_s\_l \_mbsspn \_mbsspn\_l \_mbsspnp \_mbsspnp\_l \_mbsstr \_mbsstr\_l \_mbstok \_mbstok\_l \_mbstok\_s \_mbstok\_s\_l \_mbsupr \_mbsupr\_l \_mbsupr\_s \_mbsupr\_s\_l is\_wctype|マルチバイト文字列はUWP アプリではサポートされていません。|代わりに、Unicode 文字列を使用します。|  
|\_pclose \_pipe \_popen \_wpopen|パイプ機能は UWP アプリには使用できません。|回避策はありません。|  
|\_resetstkoflw|サポートする Win32 API は UWP アプリでは使用できません。|回避策はありません。|  
|\_getsystime \_setsystime|これらは以前のバージョンの CRT で廃止された API です。 また、ユーザーはアクセス許可がないため、UWP アプリのシステム時刻を設定できません。|システム時刻のみを取得するには、Win32 API `GetSystemTime` を使用します。 システム時刻は設定できません。|  
|\_environ \_putenv \_putenv\_s \_searchenv \_searchenv\_s \_dupenv\_s \_wputenv \_wputenv\_s \_wsearchenv getenv getenv\_s putenv \_wdupenv\_s \_wenviron \_wgetenv \_wgetenv\_s \_wsearchenv\_s tzset|UWP アプリでは環境変数を使用できません。|回避策はありません。 タイム ゾーンを設定するには、\_tzset を使用します。|  
|\_loaddll \_getdllprocaddr \_unloaddll|これらは以前のバージョンの CRT で廃止された関数です。 また、ユーザーは同じアプリケーション パッケージのものを除き、DLL を読み込むことができません。|パッケージ化された DLL を読み込んで使用するには、Win32 API `LoadPackagedLibrary`、`GetProcAddress`、`FreeLibrary` を使用します。|  
|\_wexecl \_wexecle \_wexeclp \_wexeclpe \_wexecv \_wexecve \_wexecvp \_wexecvpe \_execl \_execle \_execlp \_execlpe \_execv \_execve \_execvp \_execvpe \_spawnl \_spawnle \_spawnlp \_spawnlpe \_spawnv \_spawnve \_spawnvp \_spawnvpe \_wspawnl \_wspawnle \_wspawnlp \_wspawnlpe \_wspawnv \_wspawnve \_wspawnvp \_wspawnvpe \_wsystem execl execle execlp execlpe execv execve execvp execvpe spawnl spawnle spawnlp spawnlpe spawnv spawnve spawnvp spawnvpe system|この機能は、UWP アプリでは使用できません。 UWP アプリから別の UWP アプリまたはデスクトップ アプリを起動することはできません。|回避策はありません。|  
|\_heapwalk \_heapadd \_heapchk \_heapset \_heapused|ここに挙げた関数は通常、ヒープを使用するために使用します。 しかし、UWP アプリでは対応する Win32 API がサポートされていません。 アプリがプライベート ヒープを作成したり使用したりすることはありません。|回避策はありません。 ただし、`_heapwalk` はデバッグを目的とする場合にのみ DEBUG CRT で使用できます。 Windows ストアにアップロードされるアプリでこれらを使用することはできません。|  
  
 以下の関数は UWP アプリの CRT で使用可能ですが、大きなコード ベースを移植する場合など、対応する Win32 または [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] API が使用できない場合にのみ使用することをお勧めします。  
  
|||  
|-|-|  
|1 バイト文字列関数 \(`strcat`、`strcpy`、`strlwr` など\)。|公開されているすべての Win32 API と [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] API では Unicode 文字セットのみが使用されているため、UWP アプリには Unicode 以外の文字を使用しないようにする必要があります。 1 バイトの関数は、大きなコード ベースを移植するときのために残されていますが、それ以外の状況では使用を避け、可能な限り対応するワイド文字関数を使用してください。|  
|ストリーム IO 関数と低レベル ファイル IO 関数 \(`fopen`、`open` など\)。|ここに挙げた関数は同期的であるため、UWP アプリに使用することは勧められていません。 UWP アプリでは、UI スレッドがロックされることがないように、ファイルを開くとき、ファイルから読み取るとき、ファイルに書き込むときは非同期 API を使用します。 このような API には、`Windows::Storage::FileIO` クラスのものなどが挙げられます。|  
  
## Windows 8.x ストア アプリと Windows Phone 8.x アプリ  
 前述した API に加えて、次の API を Windows 8.x ストア アプリと Windows Phone 8.x アプリで使用することはできません。  
  
||||  
|-|-|-|  
|\_beginthread \_beginthreadex \_endthread \_endthreadex|Windows 8.x ストア アプリで Win32 API をスレッド化することはできません。|代わりに `Windows Runtime Windows::System::Threading::ThreadPool` または `concurrency::task` を使用します。|  
|\_chdir \_wchdir \_getcwd \_getdcwd \_wgetcwd \_wgetdcwd|作業ディレクトリの概念は Windows 8.x ストア アプリには適用されません。|代わりに完全パスを使用します。|  
|\_getpid|この関数は以前のバージョンの CRT で廃止されています。|Win32 API `GetCurrentProcessId()` を使用します。|  
|\_isleadbyte\_l \_ismbbalnum, \_ismbbalnum\_l, \_ismbbalpha, \_ismbbalpha \_ismbbalpha\_l \_ismbbgraph \_ismbbgraph\_l \_ismbbkalnum \_ismbbkalnum\_l \_ismbbkana \_ismbbkana\_l \_ismbbkprint \_ismbbkprint\_l \_ismbbkpunct \_ismbbkpunct\_l \_ismbblead \_ismbblead\_l \_ismbbprint \_ismbbprint\_l \_ismbbpunct \_ismbbpunct\_l \_ismbbtrail \_ismbbtrail\_l \_ismbslead \_ismbslead\_l \_ismbstrail \_ismbstrail\_l \_mbsdup isleadbyte|Windows 8.x ストア アプリではマルチバイト文字列がサポートされていません。|代わりに、Unicode 文字列を使用します。|  
|\_tzset|Windows 8.x ストア アプリでは環境変数を使用できません。|回避策はありません。|  
|\_get\_heap\_handle、\_heapmin|Windows 8.x ストア アプリでは対応する Win32 API がサポートされません。 アプリでプライベート ヒープを作成できなくなりました。|回避策はありません。 ただし、`_get_heap_handle` はデバッグを目的とする場合にのみ DEBUG CRT で使用できます。|