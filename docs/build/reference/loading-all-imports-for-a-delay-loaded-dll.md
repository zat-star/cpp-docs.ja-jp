---
title: "遅延読み込みされた DLL に対するすべてのインポートの読み込み | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__HrLoadAllImportsForDll リンカー オプション"
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 遅延読み込みされた DLL に対するすべてのインポートの読み込み
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

delayhlp.cpp で定義される **\_\_HrLoadAllImportsForDll** 関数は、[\/delayload](../../build/reference/delayload-delay-load-import.md) リンカー オプションで指定された DLL からすべてのインポートを読み込むようにリンカーに指示します。  
  
 すべてのインポートを読み込むと、コードの内の 1 か所でエラー処理を行うことができます。実際のインポートの各呼び出し部分で例外処理を使用する必要はありません。  また、ヘルパー コードがインポートの読み込みに失敗したために、アプリケーションが処理中に部分的なエラーを発生する状況を回避できます。  
  
 **\_\_HrLoadAllImportsForDll** の呼び出しによって、フックやエラー処理の動作が変更されることはありません。詳細については、「[エラー処理と通知](../../build/reference/error-handling-and-notification.md)」を参照してください。  
  
 **\_\_HrLoadAllImportsForDll** に渡された DLL 名は、その DLL の内部に格納されていた名前と比較されます \(大文字小文字は区別されます\)。  
  
 **\_\_HrLoadAllImportsForDll** の呼び出し方法について、次に例を示します。  
  
```  
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {  
   printf ( "failed on snap load, exiting\n" );  
   exit(2);  
}  
```  
  
## 参照  
 [リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)