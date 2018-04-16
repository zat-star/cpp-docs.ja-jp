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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9694eb05a2d14ff8dac49c0e9a3cb29dcf52bbac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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