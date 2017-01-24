---
title: "定義と宣言 (C) | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "エクスポート関数"
ms.assetid: d150395a-89d4-4298-9ac4-08f84fe1261c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 定義と宣言 (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 DLL インターフェイスは、システム内のプログラムによってエクスポートされることがわかっているすべての項目 \(関数とデータ\)、つまり、**dllimport** または `dllexport` として宣言されたすべての項目を参照します。  DLL インターフェイスに含まれるすべての宣言では、**dllimport** か `dllexport` の属性を指定する必要があります。  ただし、定義で指定できるのは `dllexport` 属性のみです。  たとえば、次の関数定義はコンパイラ エラーになります。  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
DllImport int func()    /* Error; dllimport prohibited in */  
                        /* definition. */  
{  
   return 1;  
}  
```  
  
 次のコードでも、エラーが生成します。  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
DllImport int i = 10;      /* Error; this is a definition. */  
```  
  
 ただし、次に示す構文は、正しい構文です。  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
DllExport int i = 10;      /* Okay: this is an export definition. */  
```  
  
 `dllexport` の使用は定義を意味し、**dllimport** は宣言を意味します。  宣言を強制するには、`dllexport` と共に `extern` キーワードを使用する必要があります。このようにしない場合、暗黙の定義になります。  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
extern DllImport int k;   /* These are correct and imply */  
Dllimport int j;          /* a declaration. */      
```  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [DLL インポートおよびエクスポート関数](../Topic/DLL%20Import%20and%20Export%20Functions.md)