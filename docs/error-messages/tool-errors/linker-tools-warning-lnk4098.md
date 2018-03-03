---
title: "リンカー ツールの警告 LNK4098 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4098
dev_langs:
- C++
helpviewer_keywords:
- LNK4098
ms.assetid: 1f1b1408-1316-4e34-80f5-6a02f2db0ac1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b199c19417d7d3be866109fff7361fb4ead959d2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4098"></a>リンカー ツールの警告 LNK4098
defaultlib 'library' と競合していますが; 他のライブラリの使用/NODEFAULTLIB:library を使用してください。  
  
 互換性のないライブラリとリンクしようとするとします。  
  
> [!NOTE]
>  ランタイム ライブラリには、さまざまな種類が混在しないためのディレクティブが含まれています。 この警告のさまざまな種類を使用するか、デバッグしようとする場合と非デバッグ バージョンのランタイム ライブラリは、同じプログラムで表示されます。 たとえば、(たとえば、マルチ スレッドではなく単一スレッドなど) 別の種類を使用するファイルし、それらをリンクしようとしています。 もう 1 種類のランタイム ライブラリのいずれかを使用する 1 つのファイルをコンパイルする場合は、この警告が表示されます。 同じランタイム ライブラリを使用するすべてのソース ファイルをコンパイルする必要があります。 参照してください、[ランタイム ライブラリの使用](../../build/reference/md-mt-ld-use-run-time-library.md)(**/MD**、 **/MT**、 **/LD**) 詳細については、コンパイラ オプション。  
  
 リンカーを使用する[/VERBOSE:LIB](../../build/reference/verbose-print-progress-messages.md)スイッチをリンカーが検索するライブラリを決定します。 非デバッグ ランタイム ライブラリ、使用の LNK4098 し、実行可能ファイルを使用して、たとえば、シングル スレッドを作成する場合に発生した場合、 **/VERBOSE:LIB**リンカーが検索するライブラリを検索するにはオプションです。 リンカーは、検索されたライブラリとして LIBC.lib、LIBCMT.lib、MSVCRT.lib、LIBCD.lib、LIBCMTD.lib、しなかったり MSVCRTD.lib を印刷する必要があります。 使用して、正しくないランタイム ライブラリを無視するようにリンカーに指示することができます[/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md)を無視するライブラリごとにします。  
  
 次の表では、使用する場合、ランタイム ライブラリによって、どのライブラリを無視するかを示します。  
  
|このランタイム ライブラリを使用するには|これらのライブラリを無視します。|  
|-----------------------------------|----------------------------|  
|シングル スレッド (libc.lib)|libcmt.lib、msvcrt.lib、libcd.lib、libcmtd.lib、msvcrtd.lib|  
|マルチ スレッド (libcmt.lib)|libc.lib、msvcrt.lib、libcd.lib、libcmtd.lib、msvcrtd.lib|  
|マルチ スレッド DLL (msvcrt.lib) を使用します。|libc.lib、libcmt.lib、libcd.lib、libcmtd.lib、msvcrtd.lib|  
|シングル スレッド (libcd.lib) のデバッグします。|libc.lib、libcmt.lib、msvcrt.lib、libcmtd.lib、msvcrtd.lib|  
|マルチ スレッド (libcmtd.lib) のデバッグします。|libc.lib、libcmt.lib、msvcrt.lib、libcd.lib、msvcrtd.lib|  
|DLL (msvcrtd.lib) を使用するマルチ スレッドをデバッグします。|libc.lib、libcmt.lib、msvcrt.lib、libcd.lib、libcmtd.lib|  
  
 たとえば、この警告を受信した非デバッグ、シングル スレッドのバージョンのランタイム ライブラリを使用する実行可能ファイルを作成する場合は、リンカー、次のオプションを使用する可能性があります。  
  
```  
/NODEFAULTLIB:libcmt.lib /NODEFAULTLIB:msvcrt.lib /NODEFAULTLIB:libcd.lib /NODEFAULTLIB:libcmtd.lib /NODEFAULTLIB:msvcrtd.lib  
```