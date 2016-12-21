---
title: "コンストラクターを持たないクラスと構造体の初期化 (C++) | Microsoft Docs"
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
ms.assetid: 3e55c3d6-1c6b-4084-b9e5-221b151402f4
caps.latest.revision: 3
caps.handback.revision: 1
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# コンストラクターを持たないクラスと構造体の初期化 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラスのコンストラクターの定義は、コンストラクターが比較的単純な場合は特に、必ずしも必要ではありません。  ユーザーは、次の例に示すように、均一初期化を使用してクラスまたは構造体のオブジェクトを初期化できます。  
  
```  
struct TempData  
{  
    int StationId;  
    time_t time;  
    double current;  
    double max;  
    double min;  
};  
  
int _tmain(int argc, _TCHAR* argv[])  
{  
    // Member initialization:  
    TempData td { 45978, GetCurrentTime(), 28.9, 37.0, 16.7 };  
  
    // Default initialization = {0,0,0,0,0}  
    TempData td_default {};  
  
    //Error C4700 uninitialized local variable  
    TempData td_noInit;   
    return 0;  
}  
```  
  
## 参照  
 [クラスと構造体](../Topic/Classes%20and%20Structs%20\(C++\).md)   
 [コンストラクター](../cpp/constructors-cpp.md)