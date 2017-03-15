---
title: "/DEBUGTYPE (デバッグ情報オプション) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/debugtype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DEBUGTYPE リンカー オプション"
  - "DEBUGTYPE リンカー オプション"
  - "-DEBUGTYPE リンカー オプション"
ms.assetid: 1ddcb718-7fec-4f92-a319-3f70f04fe742
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# /DEBUGTYPE (デバッグ情報オプション)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/DEBUGTYPE オプションは、\/DEBUG オプションによって生成されるデバッグ情報の種類を指定します。  
  
```  
/DEBUGTYPE:[CV | PDATA | FIXUP]  
```  
  
## 引数  
 CV  
 シンボル、行番号、その他のオブジェクトのコンパイル情報のデバッグ情報を PDB ファイルに出力するようにリンカーに指示します。  既定では、**\/DEBUG** が指定されていて **\/DEBUGTYPE** が指定されていないときにこのオプションが有効になります。  
  
 PDATA  
 .pdata エントリと .xdata エントリを PDB ファイル内のデバッグ ストリーム情報に追加するようにリンカーに指示します。  既定では、**\/DEBUG** オプションと **\/DRIVER** オプションの両方が指定されているときにこのオプションが有効になります。  **\/DEBUGTYPE:PDATA** だけが指定されている場合、リンカーは自動的にデバッグ シンボルを PDB ファイルに含めます。  **\/DEBUGTYPE:PDATA,FIXUP** が指定されている場合、リンカーはデバッグ シンボルを PDB ファイルに含めません。  
  
 FIXUP  
 再配置テーブル エントリを PDB ファイル内のデバッグ ストリーム情報に追加するようにリンカーに指示します。  既定では、**\/DEBUG** オプションと **\/PROFILE** オプションの両方が指定されているときにこのオプションが有効になります。  **\/DEBUGTYPE:FIXUP** または **\/DEBUGTYPE:FIXUP,PDATA** が指定されている場合、リンカーはデバッグ シンボルを PDB ファイルに含めません。  
  
 **\/DEBUGTYPE** の引数は、コンマで区切って任意の順序で組み合わせることができます。  **\/DEBUGTYPE** オプションとその引数では、大文字と小文字は区別されません。  
  
## 解説  
 **\/DEBUGTYPE** オプションを使用して、再配置テーブル データまたは .pdata および .xdata ヘッダー情報をデバッグ ストリームに含めることを指定します。  これにより、リンカーは、カーネルモード コードで中断するときにカーネル デバッガーに表示されるユーザーモード コードに関する情報を含めます。  **FIXUP** が指定されたときにデバッグ シンボルを使用できるようにするには、**CV** 引数を含めます。  
  
 アプリケーションで一般的に使用されるユーザー モードのコードをデバッグするには、**\/DEBUGTYPE** オプションは必要ありません。  既定では、デバッグの出力を指定するコンパイラ スイッチ \([\/Z7、\/Zi、\/ZI](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md)\) によって、Visual Studio デバッガーで必要なすべての情報が出力されます。  ユーザーモード コンポーネントとカーネルモード コンポーネントを組み合わせたコード \(デバイス ドライバーの構成アプリなど\) をデバッグするには、**\/DEBUGTYPE:PDATA** または **\/DEBUGTYPE:CV,PDATA,FIXUP** を使用します。  カーネル モード デバッガーの詳細については、[Windows 用デバッグ ツール \(WinDbg、KD、CDB、NTSD\)](http://go.microsoft.com/fwlink/p?LinkID=285651) に関するページを参照してください。  
  
## 参照  
 [\/DEBUG \(デバッグ情報の生成\)](../../build/reference/debug-generate-debug-info.md)   
 [\/DRIVER \(Windows NT カーネル モード ドライバー\)](../../build/reference/driver-windows-nt-kernel-mode-driver.md)   
 [\/PROFILE \(パフォーマンス ツール プロファイラー\)](../../build/reference/profile-performance-tools-profiler.md)   
 [Windows 用デバッグ ツール \(WinDbg、KD、CDB、NTSD\)](http://go.microsoft.com/fwlink/p?LinkID=285651)