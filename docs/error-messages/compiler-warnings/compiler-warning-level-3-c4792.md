---
title: "コンパイラの警告 (レベル 3) C4792 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4792
dev_langs:
- C++
helpviewer_keywords:
- C4792
ms.assetid: c047ce69-a622-44e1-9425-d41aa9261c61
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 7886d2b28c9120e2e764dedd0ecc72265fe91be5
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-3-c4792"></a>コンパイラの警告 (レベル 3) C4792
sysimport を使用して関数 'function' が宣言され、ネイティブ コードから参照されました。インポート ライブラリはリンクする必要があります  
  
 DllImport を使用してプログラムにインポートされたネイティブ関数が、アンマネージ関数から呼び出されました。 そのため、DLL のインポート ライブラリにリンクする必要があります。  
  
 コード内、またはコンパイル方法の変更でこの警告を解決することはできません。 使用して、[警告](../../preprocessor/warning.md)プラグマをこの警告を無効にします。  
  
 次の例では C4792 が生成されます。  
  
```  
// C4792.cpp  
// compile with: /clr /W3  
// C4792 expected  
using namespace System::Runtime::InteropServices;  
[DllImport("msvcrt")]  
extern "C" int __cdecl puts(const char *);  
int main() {}  
  
// Uncomment the following line to resolve.  
// #pragma warning(disable : 4792)  
#pragma unmanaged  
void func(void){  
   puts("test");  
}  
```
