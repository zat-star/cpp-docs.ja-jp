---
title: "コンパイラの警告 (レベル 1) C4747 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4747
dev_langs:
- C++
helpviewer_keywords:
- C4747
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 7ecbfe8e2ace06cb6e667d77d315f544ce0b451c
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4747"></a>コンパイラの警告 (レベル 1) C4747
マネージ 'entrypoint' を呼び出す: マネージ コードは、DLL エントリ ポイントおよび DLL エントリ ポイントから到達した呼び出しを含むローダー ロックでは実行されません  
  
 MSIL にコンパイルされる可能性がある) DLL エントリ ポイントが検出されました。  エントリ ポイントが MSIL にコンパイルされた DLL の読み込み中に潜在的な問題があるため DLL エントリ ポイント関数を MSIL にコンパイルを強くお勧めしています。  
  
 詳細については、次を参照してください。[混在アセンブリの初期化](../../dotnet/initialization-of-mixed-assemblies.md)と[リンカ ツール エラー LNK1306](../../error-messages/tool-errors/linker-tools-error-lnk1306.md)します。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  使用して、モジュールをコンパイルしないで**/clr**します。  
  
2.  エントリ ポイント関数をマーク`#pragma unmanaged`します。  
  
## <a name="example"></a>例  
 次の例では、C4747 を生成します。  
  
```  
// C4747.cpp  
// compile with: /clr /c /W1  
// C4747 expected  
#include <windows.h>  
  
// Uncomment the following line to resolve.  
// #pragma unmanaged  
  
BOOL WINAPI DllMain(HANDLE hInstance, ULONG Command, LPVOID Reserved) {  
   return TRUE;  
};  
```
