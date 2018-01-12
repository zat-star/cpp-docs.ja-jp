---
title: "Cl.exe の戻り値 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: cl.exe compiler, return value
ms.assetid: 7c2d7f33-ee0d-4199-8ef4-75fe2b007670
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 85ca64178a4914cfbbc8b3a717b87ab5590cd778
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="return-value-of-clexe"></a>cl.exe の戻り値
cl.exe では、動作が正常終了した場合 (エラーがない場合) は 0 を返し、それ以外の場合は 0 以外の値を返します。  
  
 スクリプト、PowerShell、.cmd、または .bat ファイルからコンパイルを行う場合は、cl.exe の戻り値が役に立ちます。 エラーまたは警告が発生した場合にそれらを解決できるように、コンパイラの出力をキャプチャすることをお勧めします。  
  
 cl.exe のエラー終了コードは多すぎて、すべてを表示することはできません。 Winerror.h で、エラー コードを検索するにまたは ntstatus.h ファイルに含まれ、Windows ソフトウェア開発キット % (x86) %\Windows キット\\`version`\Include\shared\ ディレクトリ。 10 進数で返されるエラー コードは、16 進数に変換して検索する必要があります。 たとえば、16 進数に変換された -1073741620 エラー コードは 0xC00000CC です。 このエラーは ntstatus.h にあり、対応するメッセージは "指定した共有名がリモート サーバーで見つかりません" です。 Windows エラー コードのダウンロード可能な一覧は、次を参照してください。 [& #91。MS ERREF &#93;: Windows エラー コード](http://msdn.microsoft.com/library/cc231196)です。  
  
 Visual Studio でエラー ルックアップ ユーティリティを使用して、コンパイラ エラー メッセージの意味を検索することもできます。 Visual Studio のコマンド シェルでは、次のように入力します。 **errlook.exe** ; ユーティリティを起動またはメニュー バーで、Visual Studio IDE で次のように選択します。**ツール**、**エラー ルックアップ**です。 エラー値を入力して、そのエラーに関連付けられている説明のテキストを見つけます。 詳細については、次を参照してください。 [ERRLOOK リファレンス](../../build/reference/errlook-reference.md)です。  
  
## <a name="remarks"></a>コメント  
 次に、cl.exe の戻り値を使用するサンプル .bat ファイルを示します。  
  
```  
echo off  
cl /W4 t.cpp  
@if ERRORLEVEL == 0 (  
   goto good  
)  
  
@if ERRORLEVEL != 0 (  
   goto bad  
)  
  
:good  
   echo "clean compile"  
   echo %ERRORLEVEL%  
   goto end  
  
:bad  
   echo "error or warning"  
   echo %ERRORLEVEL%  
   goto end  
  
:end  
```  
  
## <a name="see-also"></a>参照  
 [コンパイラ コマンド ラインの構文](../../build/reference/compiler-command-line-syntax.md)