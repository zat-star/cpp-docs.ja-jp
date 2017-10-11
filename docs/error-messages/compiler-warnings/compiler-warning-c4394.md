---
title: "コンパイラの警告 C4394 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4394
dev_langs:
- C++
helpviewer_keywords:
- C4394
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5b201b95a2ec9d43c904de35ca581efbf31b7526
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4394"></a>コンパイラの警告 C4394
'関数' : appdomain ごとのシンボルは __declspec(dllexport) と共に設定することはできません  
  
 マークされた関数、 [appdomain](../../cpp/appdomain.md) `__declspec`修飾子が MSIL にではなくネイティブ)、およびエクスポート テーブルにコンパイルされる ([エクスポート](../../windows/export.md)`__declspec`修飾子) はマネージ関数のサポートされていません。  
  
 public アクセシビリティを持つようにマネージ関数を宣言できます。 詳細については、次を参照してください。[可視性を入力](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)と[メンバーの可視性](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility)です。  
  
 C4394 は、常にエラーとして表示されます。  この警告をオフにすることができます、`#pragma warning`または**/wd**; を参照してください[警告](../../preprocessor/warning.md)または[/w、/W0、/W1、/W2、/W3、/W4、/w1、/w2、/w3、/w4、/Wall、/wd、//wo、/Wv、/WX (警告レベル)](../../build/reference/compiler-option-warning-level.md)詳細についてはします。  
  
## <a name="example"></a>例  
 次の例では、C4394 を生成します。  
  
```  
// C4394.cpp  
// compile with: /clr /c  
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394  
__declspec(dllexport) int g2 = 0;   // OK  
```
