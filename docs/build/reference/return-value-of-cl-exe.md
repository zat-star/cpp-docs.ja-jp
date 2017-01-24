---
title: "cl.exe の戻り値 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe コンパイラ, 戻り値"
ms.assetid: 7c2d7f33-ee0d-4199-8ef4-75fe2b007670
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# cl.exe の戻り値
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

cl.exe では、動作が正常終了した場合 \(エラーがない場合\) は 0 を返し、それ以外の場合は 0 以外の値を返します。  
  
 スクリプト、PowerShell、.cmd、または .bat ファイルからコンパイルを行う場合は、cl.exe の戻り値が役に立ちます。  エラーまたは警告が発生した場合にそれらを解決できるように、コンパイラの出力をキャプチャすることをお勧めします。  
  
 cl.exe のエラー終了コードは多すぎて、すべてを表示することはできません。  %ProgramFiles\(x86\)%\\Windows Kits\\`version`\\Include\\shared\\ ディレクトリにある Windows Software Development Kit に含まれる winerror.h ファイルまたは ntstatus.h ファイルで、エラー コードを検索できます。  10 進数で返されるエラー コードは、16 進数に変換して検索する必要があります。  たとえば、16 進数に変換された \-1073741620 エラー コードは 0xC00000CC です。  このエラーは ntstatus.h にあり、対応するメッセージは "指定した共有名がリモート サーバーで見つかりません" です。ダウンロード可能な Windows エラー コードの一覧については、「[&#91;MS\-ERREF&#93;: Windows Error Codes](http://msdn.microsoft.com/ja-jp/1bc92ddf-b79e-413c-bbaa-99a5281a6c90)」を参照してください。  
  
 Visual Studio でエラー ルックアップ ユーティリティを使用して、コンパイラ エラー メッセージの意味を検索することもできます。  Visual Studio コマンド シェルで、「**errlook.exe**」と入力してユーティリティを開始するか、Visual Studio IDE のメニュー バーで、**\[ツール\]**、**\[エラー ルックアップ\]** の順に選択します。  エラー値を入力して、そのエラーに関連付けられている説明のテキストを見つけます。  詳細については、「[ERRLOOK リファレンス](../../build/reference/errlook-reference.md)」を参照してください。  
  
## 解説  
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
  
## 参照  
 [コンパイラ コマンド ラインの構文](../../build/reference/compiler-command-line-syntax.md)