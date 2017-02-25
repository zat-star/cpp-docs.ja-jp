---
title: "コンパイラの警告 C4368 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4368"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4368"
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# コンパイラの警告 C4368
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'メンバー' をマネージ '型' のメンバーとして定義できません。混合型はサポートされていません  
  
 CLR 型にネイティブ データ メンバーを埋め込むことはできません。  
  
 ただし、ネイティブ型へのポインターを宣言し、その有効期間をマネージ クラスのコンストラクター、デストラクター、およびファイナライザーで制御することはできます。  詳細については、「[デストラクターとファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)」を参照してください。  
  
 この警告は、常にエラーとして表示されます。  C4368 を無効にするには、[warning](../../preprocessor/warning.md) プラグマを使用します。  
  
## 使用例  
 次の例では C4368 エラーが生成されます。  
  
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