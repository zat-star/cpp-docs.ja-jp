---
title: "ref new, gcnew  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "gcnew"
  - "ref new"
  - "gcnew_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ref new keyword (C++)"
  - "gcnew keyword [C++]"
ms.assetid: 388a62da-c2df-4a94-a9a2-205b53e577da
caps.latest.revision: 24
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ref new, gcnew  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`ref new` 集計キーワードは、オブジェクトがアクセスできなくなったときにガベージ コレクションによって収集され、割り当てられたオブジェクトへのハンドル \([^](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)\) を返す型のインスタンスを割り当てます。  
  
## すべてのランタイム  
 `ref new` によって割り当てられた型のインスタンスのメモリは、自動的に解放されます。  
  
 `ref new` 演算では、メモリを割り当てることができないと `OutOfMemoryException` がスローされます。  
  
 ネイティブ C\+\+ 型のメモリの割り当てと解放の詳細については、「[new および delete 演算子](../cpp/new-and-delete-operators.md)」を参照してください。  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 有効期間が自動的に管理される Windows ランタイム オブジェクトのメモリを割り当てるには、`ref new` を使用します。  オブジェクトは、参照の最後のコピーがスコープ外になった後で参照カウントが 0 になると、自動的に解放されます。  詳細については、「[Ref クラスと構造体](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx)」を参照してください。  
  
### 必要条件  
 コンパイラ オプション: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 マネージ型 \(参照型または値型\) のメモリは `gcnew` によって割り当てられ、ガベージ コレクションによって解放されます。  
  
### 必要条件  
 コンパイラ オプション: **\/clr**  
  
### 使用例  
 **例**  
  
 次の例では、`gcnew` を使用して Message オブジェクトを割り当てています。  
  
```  
// mcppv2_gcnew_1.cpp  
// compile with: /clr  
ref struct Message {  
   System::String^ sender;  
   System::String^ receiver;  
   System::String^ data;  
};  
  
int main() {  
   Message^ h_Message  = gcnew Message;  
  //...  
}  
```  
  
 **例**  
  
 次の例では、`gcnew` を使用して、参照型のように使用するボックス化された値型を作成しています。  
  
```  
// example2.cpp : main project file.  
// compile with /clr  
using namespace System;  
value class Boxed {  
    public:  
        int i;  
};  
int main()  
{  
    Boxed^ y = gcnew Boxed;  
    y->i = 32;  
    Console::WriteLine(y->i);  
    return 0;  
}  
```  
  
 **出力**  
  
  **32**   
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)