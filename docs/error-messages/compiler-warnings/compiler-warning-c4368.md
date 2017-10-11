---
title: "コンパイラの警告 C4368 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4368
dev_langs:
- C++
helpviewer_keywords:
- C4368
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6fd66d8fb6d30a960c659345910242ec5a1a2e11
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4368"></a>コンパイラの警告 C4368
'メンバー' をマネージ '型' のメンバーとして定義できません。混合型はサポートされていません  
  
 CLR 型にネイティブ データ メンバーを埋め込むことはできません。  
  
 ただし、ネイティブ型へのポインターを宣言し、その有効期間をマネージ クラスのコンストラクター、デストラクター、およびファイナライザーで制御することはできます。 詳細については、次を参照してください。[デストラクターおよびファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)です。  
  
 この警告は、常にエラーとして表示されます。 使用して、[警告](../../preprocessor/warning.md)プラグマ C4368 を無効にします。  
  
## <a name="example"></a>例  
 次の例では、C4368 を生成します。  
  
```  
// C4368.cpp  
// compile with: /clr /c  
struct N {};  
ref struct O {};  
ref struct R {  
    R() : m_p( new N ) {}  
    ~R() { delete m_p; }  
  
   property N prop;   // C4368  
   int i[10];   // C4368  
  
   property O ^ prop2;   // OK  
   N * m_p;   // OK  
};  
```
