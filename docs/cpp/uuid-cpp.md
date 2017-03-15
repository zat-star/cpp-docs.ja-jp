---
title: "uuid (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "uuid"
  - "uuid_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec キーワード [C++], uuid"
  - "uuid __declspec キーワード"
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# uuid (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 コンパイラは、`uuid` 属性で宣言または定義された \(完全な COM オブジェクト定義のみ\) クラスまたは構造体に GUID をアタッチします。  
  
## 構文  
  
```  
  
__declspec( uuid("  
ComObjectGUID  
") ) declarator  
```  
  
## 解説  
 `uuid` 属性は、引数として文字列を受け取ります。  この文字列は、**{ }** 区切り記号を伴う標準レジストリ形式、またはこの区切り記号を伴わない標準レジストリ形式で GUID の名前を指定します。  次に例を示します。  
  
```  
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;  
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;  
```  
  
 この属性は、再宣言で適用できます。  これにより、システム ヘッダーは、**IUnknown** などのインターフェイスの定義を提供できます。また、他のヘッダー \(COMDEF.H など\) の再宣言で GUID を提供できます。  
  
 キーワード [\_\_uuidof](../cpp/uuidof-operator.md) は、ユーザー定義型に接続されている定数 GUID を取得するために適用できます。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)