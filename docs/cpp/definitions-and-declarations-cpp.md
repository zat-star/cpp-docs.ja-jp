---
title: "定義と宣言 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 56b809c0-e602-4f18-9ca5-cd7a8fbaaf30
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 定義と宣言 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 DLL インターフェイスは、システム内のプログラムによってエクスポートされることがわかっているすべての項目 \(関数とデータ\)、つまり、**dllimport** または `dllexport` として宣言されたすべての項目を参照します。  DLL インターフェイスに含まれるすべての宣言では、**dllimport** か `dllexport` の属性を指定する必要があります。  ただし、定義では、`dllexport` 属性のみを指定する必要があります。  たとえば、次の関数定義はコンパイラ エラーになります。  
  
```  
__declspec( dllimport ) int func() {   // Error; dllimport  
                                    // prohibited on definition.  
   return 1;  
}  
```  
  
 次のコードでも、エラーが生成します。  
  
```  
#define DllImport   __declspec( dllimport )  
  
__declspec( dllimport ) int i = 10;  // Error; this is a  
                                     // definition.  
```  
  
 ただし、次に示す構文は、正しい構文です。  
  
```  
__declspec( dllexport ) int i = 10;     // Okay--export definition  
```  
  
 `dllexport` の使用は定義を意味し、**dllimport** は宣言を意味します。  宣言を強制するには、`dllexport` と共に `extern` キーワードを使用する必要があります。このようにしない場合、暗黙の定義になります。  そのため、次の例は正しいコードになります。  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
extern DllImport int k; // These are both correct and imply a  
DllImport int j;        // declaration.  
```  
  
 次の例に、上記の例をさらに明確に示します。  
  
```  
static __declspec( dllimport ) int l; // Error; not declared extern.  
  
void func() {  
    static __declspec( dllimport ) int s;  // Error; not declared  
                                           // extern.  
    __declspec( dllimport ) int m;         // Okay; this is a   
                                           // declaration.  
    __declspec( dllexport ) int n;         // Error; implies external  
                                           // definition in local scope.  
    extern __declspec( dllimport ) int i;  // Okay; this is a  
                                           // declaration.  
    extern __declspec( dllexport ) int k;  // Okay; extern implies  
                                           // declaration.  
    __declspec( dllexport ) int x = 5;     // Error; implies external  
                                           // definition in local scope.  
}  
```  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [dllexport、dllimport](../cpp/dllexport-dllimport.md)