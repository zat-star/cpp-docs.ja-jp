---
title: "致命的なエラー C1189 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1189"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1189"
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# 致命的なエラー C1189
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#error : ユーザーが指定したエラー メッセージ  
  
 C1189 は `#error` ディレクティブによって生成されます。  エラー メッセージのテキストは、ディレクティブを記述する開発者が指定します。  詳細については、「[\#error ディレクティブ](../../preprocessor/hash-error-directive-c-cpp.md)」を参照してください。  
  
 次の例では C1189 エラーが生成されます。  この例では、`_WIN32` 識別子が定義されていないため、開発者がカスタム エラー メッセージを発行します。  
  
```  
// C1189.cpp  
#undef _WIN32  
#if !defined(_WIN32)  
#error _WIN32 must be defined   // C1189  
#endif  
```  
  
 **\/robust** MIDL コンパイラ オプションを使用して ATL プロジェクトをビルドした場合も、このエラーが表示されることがあります。  **\/robust** をに切り替えますビルド [!INCLUDE[win2kfamily](../../c-runtime-library/includes/win2kfamily_md.md)] のみおよび Windows のバージョンを使用します。  このエラーを解決するには、次の手順のうち 1 つを使用する:  
  
-   dlldatax.c ファイルで、次の行を変更します。  
  
```  
#define _WIN32_WINNT 0x0400   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
 この行を次のように変更します。  
  
```  
#define _WIN32_WINNT 0x0500   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
-   **\[MIDL\]** プロパティ ページ フォルダーの **\[詳細\]** プロパティ ページを使用して、**\/robust** スイッチを削除し、**\/no\_robust** スイッチを指定します。  詳細については、「[\[詳細\] \(\[MIDL\] プロパティ ページ\)](../Topic/MIDL%20Property%20Pages:%20Advanced.md)」を参照してください。  
  
## 参照  
 [\#define ディレクティブ](../../preprocessor/hash-define-directive-c-cpp.md)