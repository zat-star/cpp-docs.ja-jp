---
title: "CFixedStringT : カスタム文字列マネージャーの例 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFixedStringT クラス, 使用 (カスタム文字列マネージャーを)"
ms.assetid: 1cf11fd7-51b8-4b94-87af-02bc25f47dd6
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# CFixedStringT : カスタム文字列マネージャーの例
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL ライブラリは **CFixedStringMgr**というクラス [CFixedStringT](../atl-mfc-shared/reference/cfixedstringt-class.md)で使用するカスタム文字列マネージャーの 1 例を実行します。  `CFixedStringT` は [CStringT](../atl-mfc-shared/reference/cstringt-class.md) から文字列がである限り派生し、`CFixedStringT` のオブジェクトの一部として `CFixedStringT`の **t\_nChars** のテンプレート パラメーターで指定された長さ未満文字データ自体を割り当てる文字列を実装します。  この方法によって、文字列の長さが固定バッファーのサイズより大きく育たなければ、ヒープは必要ではありません。  文字列データを割り当てるには `CFixedStringT` がヒープを使用しないため、文字列マネージャーとして **CAtlStringMgr** を使用できません。  これは [IAtlStringMgr](../Topic/IAtlStringMgr%20Class.md) のインターフェイスを実装するカスタム文字列**CFixedStringMgr**マネージャーを使用します。  このインターフェイスは [カスタム文字列マネージャー \(高度なメソッド\) の実装](../Topic/Implementation%20of%20a%20Custom%20String%20Manager%20\(Advanced%20Method\).md)で説明します。  
  
 **CFixedStringMgr** のコンストラクターは 3 個のパラメーターを受け取ります:  
  
-   使用する `CStringData` の固定構造体への**pData:** 指すポインター。  
  
-   **nChars:** `CStringData` の構造が保持できる最大文字数。  
  
-   「バックアップ文字列マネージャーの `IAtlStringMgr` インターフェイスへの**pMgr:** 示すポインター」。  
  
 コンストラクターは、それぞれのメンバー変数に `pData` と **pMgr** の値を格納します \(`m_pData` と **m\_pMgr**\)。  次に、バッファーの長さ、固定バッファーの最大サイズと等しい使用できる長さ、– 1、参照カウントがゼロに設定します。  参照の数値は、バッファーが **CFixedStringMgr** のこのインスタンスを文字列マネージャーとして使用するロックされることを示します。  
  
 ロックされたバッファーにとしてマークすることは `CStringT` の他のインスタンスが共有バッファーへの参照を保持することを防止できます。  `CStringT` の他のインスタンスがバッファーを共有するそのほかの文字列がまだバッファーを使用して、削除する `CFixedStringT` に含まれるバッファーに対してできます。  
  
 **CFixedStringMgr** は `IAtlStringMgr` のインターフェイスの完全な実装です。  各メソッドの実装は別に説明します。  
  
## CFixedStringMgr::Allocate の実装  
 **CFixedStringMgr::Allocate** の実装では、最初に文字列の要求されたサイズが固定バッファーのサイズ以下であるかどうかを確認します \( `m_pData` のメンバーに格納されます\)。  固定バッファーのサイズが十分にある場合、はゼロ **CFixedStringMgr** の長さの固定バッファーをロックします。  文字列の長さが固定バッファーのサイズより大きく育たない限り、`CStringT` がバッファーを再割り当てする必要はありません。  
  
 文字列の要求されたサイズがより大きい固定バッファー **CFixedStringMgr** はバックアップに要求を文字列マネージャーが転送されます。  バックアップ文字列マネージャーはヒープからバッファーを割り当てると推論されます。  ただし、このバッファー **CFixedStringMgr** を返す前にバッファーをロックし、ポインターと **CFixedStringMgr** のオブジェクトにバッファーの文字列マネージャーのポインターを置き換えます。  これはことを **CFixedStringMgr**に `CStringT` の際によってバッファーを再割り当てするか、解放しようとします。  
  
## CFixedStringMgr::ReAllocate の実装  
 **CFixedStringMgr::ReAllocate** の実装は **Allocate**の実装とよく似ています。  
  
 バッファーが再割り当てされる固定バッファーであり、要求されたバッファー サイズが固定バッファーより小さい場合、代入は行われません。  ただし、バッファーが再割り当てされる固定バッファーでない場合、バックアップ マネージャーによって割り当てられたバッファーである必要があります。  この場合、バックアップ マネージャーがバッファーを再割り当てするために使用されます。  
  
 バッファーが再割り当てされる固定バッファーで、新しいバッファー サイズが固定バッファー内に収まらない場合は **CFixedStringMgr** バックアップ マネージャーを使用して新しいバッファーを割り当てます。  固定バッファーの内容が新しいバッファーにコピーします。  
  
## CFixedStringMgr::Free の実装  
 **CFixedStringMgr::Free** の実装は **Allocate** と `ReAllocate`と同じパターンに従います。  解放バッファーが固定バッファーの場合、メソッドは長さによってロックされたバッファーに設定されます。  解放バッファーをバックアップ マネージャーと、**CFixedStringMgr** 割り当てられている場合は、それを解放するためにバックアップ マネージャーを使用します。  
  
## CFixedStringMgr::Clone の実装  
 の実装 **CFixedStringMgr::Clone** ポインター自体を **CFixedStringMgr** ではなくバックアップ マネージャーに常に返します。  これは **CFixedStringMgr** のすべてのインスタンスに `CStringT`の一つのインスタンスのみに関連付けることができないためです。  マネージャーを複製することをお `CStringT` の他のインスタンスがバックアップ マネージャーを派生させる必要があります。  これは、共有されるバックアップ マネージャーのサポートです。  
  
## CFixedStringMgr::GetNilString の実装  
 **CFixedStringMgr::GetNilString** の実装は、固定バッファーを返します。  **CFixedStringMgr** と `CStringT`の一対一の対応するために、`CStringT` のインスタンスは、複数のバッファーを同時に使用できません。  したがって、未の文字列と実際の文字列バッファーは、同時に必要ではありません。  
  
 固定バッファーが使用されていない場合は、**CFixedStringMgr** は長さで初期化されることを確認します。  これは、未の文字列として使用できます。  追加されたボーナスとして、固定バッファーの `nAllocLength` のメンバーは、固定バッファーの最大サイズで常にに設定されます。  これは `CStringT` が [IAtlStringMgr::Reallocate](../Topic/IAtlStringMgr::Reallocate.md)を呼び出したりしないで文字列を拡張できることを意味します、文字列の場合は。  
  
## 要件  
 **ヘッダー:** cstringt.h  
  
## 参照  
 [CStringT によるメモリ管理](../atl-mfc-shared/memory-management-with-cstringt.md)