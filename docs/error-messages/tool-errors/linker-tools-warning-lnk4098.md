---
title: "リンカー ツールの警告 LNK4098 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4098"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4098"
ms.assetid: 1f1b1408-1316-4e34-80f5-6a02f2db0ac1
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカー ツールの警告 LNK4098
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

defaultlib 'library' は別のライブラリの使用と競合しています。\/NODEFAULTLIB:library を使用してください。  
  
 互換性がないライブラリのリンクを試みています。  
  
> [!NOTE]
>  ランタイム ライブラリには、異なる型を混合しないためのディレクティブがあります。  同じプログラムで、異なる型を使用したり、ランタイム ライブラリのデバッグ バージョンと非デバッグ バージョンを混用すると、この警告が発生します。  たとえば、1 つのファイルをある種類のランタイム ライブラリを使用するためにコンパイルし、もう 1 つのファイルでは別の種類のランタイム ライブラリを使用するためにコンパイルして \(たとえば、シングルスレッドとマルチスレッドのライブラリ\)、リンクすると、この警告が発生します。  全ファイルで同じランタイム ライブラリを使うようにコンパイルする必要があります。  詳細については、「[\/MD、\/MT、\/LD \(ランタイム ライブラリの使用\)](../../build/reference/md-mt-ld-use-run-time-library.md)」を参照してください。  
  
 リンカーの [\/VERBOSE:LIB](../../build/reference/verbose-print-progress-messages.md) スイッチで、リンカーの検索するライブラリを決めることができます。  LNK4098 が発生しているときに、たとえばシングルスレッドで非デバッグ モードのライブラリを使用する実行可能ファイルを作成する場合は、**\/VERBOSE:LIB** オプションを使用してリンカーが検索するライブラリを調べることができます。  リンカーはライブラリの検索時に LIBC.lib を出力しますが、LIBCMT.lib、MSVCRT.lib、LIBCD.lib、LIBCMTD.lib、MSVCRTD.lib は出力しません。  無視するライブラリごとに [\/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) を使用すると、不適切なランタイム ライブラリを無視するようにリンカーに指示できます。  
  
 使用するライブラリによってどのライブラリを無視した方がよいかを次の表に示します。  
  
|使用するランタイム ライブラリ|無視するライブラリ|  
|---------------------|---------------|  
|シングルスレッド \(libc.lib\)|libcmt.lib、msvcrt.lib、libcd.lib、libcmtd.lib、msvcrtd.lib|  
|マルチスレッド \(libcmt.lib\)|libc.lib、msvcrt.lib、libcd.lib、libcmtd.lib、msvcrtd.lib|  
|DLL を使用するマルチスレッド \(msvcrt.lib\)|libc.lib、libcmt.lib、libcd.lib、libcmtd.lib、msvcrtd.lib|  
|デバッグ用のシングルスレッド \(libcd.lib\)|libc.lib、libcmt.lib、msvcrt.lib、libcmtd.lib、msvcrtd.lib|  
|デバッグ用のマルチスレッド \(libcmtd.lib\)|libc.lib、libcmt.lib、msvcrt.lib、libcd.lib、msvcrtd.lib|  
|DLL を使用するデバッグ用のマルチスレッド \(msvcrtd.lib\)|libc.lib、libcmt.lib、msvcrt.lib、libcd.lib、libcmtd.lib|  
  
 たとえば、この警告を受信したときに、非デバッグ モードのシングルスレッドのランタイム ライブラリを使用する場合には、次のリンカー オプションを使用します。  
  
```  
/NODEFAULTLIB:libcmt.lib /NODEFAULTLIB:msvcrt.lib /NODEFAULTLIB:libcd.lib /NODEFAULTLIB:libcmtd.lib /NODEFAULTLIB:msvcrtd.lib  
```