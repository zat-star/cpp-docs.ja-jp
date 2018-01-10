---
title: "クラスとコンス トラクター (C++) を持たない構造体の初期化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
ms.assetid: 3e55c3d6-1c6b-4084-b9e5-221b151402f4
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c65bc0adb32d61cef76e02aa944826eaf866c7c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="initializing-classes-and-structs-without-constructors-c"></a>コンストラクターを持たないクラスと構造体の初期化 (C++)
クラスのコンストラクターの定義は、コンストラクターが比較的単純な場合は特に、必ずしも必要ではありません。 ユーザーは、次の例に示すように、均一初期化を使用してクラスまたは構造体のオブジェクトを初期化できます。  
  
```  
#include "stdafx.h"  
#include <Windows.h>  
  
// No constructor  
struct TempData  
{  
    int StationId;  
    time_t time;  
    double current;  
    double maxTemp;  
    double minTemp;  
};  
  
// Has a constructor  
struct TempData2  
{  
    TempData2(double minimum, double maximum, double cur, int id, time_t t) :  
       minTemp(minimum), maxTemp(maximum), current(cur), stationId(id), time(t) {}  
    int stationId;  
    time_t time;  
    double current;  
    double maxTemp;  
    double minTemp;  
};  
  
int main()  
{  
    // Member initialization (in order of declaration):  
    TempData td{ 45978, GetCurrentTime(), 28.9, 37.0, 16.7 };  
  
    // Default initialization = {0,0,0,0,0}  
    TempData td_default{};  
  
    //Error C4700 uninitialized local variable  
    TempData td_noInit;  
  
    // Member declaration (in order of ctor parameters)  
    TempData2 td2{ 16.7, 37.0, 28.9, 45978, GetCurrentTime() };  
  
    return 0;  
}  
  
```  
  
 クラスまたは構造体は、コンス トラクターを持たない、ときに、メンバーが、クラスで宣言された順序でリスト要素を提供することに注意してください。 クラスにコンス トラクターがある場合は、パラメーターの順序で要素を指定します。  
  
## <a name="see-also"></a>参照  
 [クラスと構造体](../cpp/classes-and-structs-cpp.md)   
 [コンストラクター](../cpp/constructors-cpp.md)