---
title: "格納と読み込みのアーカイブを通じた Cobject |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CObject
dev_langs: C++
helpviewer_keywords:
- CObjects [MFC], loading through archives
- CArchive class [MFC], storing and loading objects
- Serialize method, vs. CArchive operators
- CObject class [MFC], CArchive objects
- CObjects [MFC]
ms.assetid: a829b6dd-bc31-47e0-8108-fbb946722db9
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 987f754ccdf03e5a252feae693a1f7718da1b353
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>アーカイブを通じた CObject の格納と読み込み
格納と読み込み`CObject`アーカイブを通じた s は注意が必要です。 場合によってを呼び出す必要があります、`Serialize`関数、オブジェクトの場所、`CArchive`オブジェクトがパラメーターでの`Serialize`を使用してではなく、呼び出し、  **< \<** または **>>** の演算子、`CArchive`です。 注意する重要な実際には、 `CArchive`  **>>** 演算子コンストラクト、`CObject`に基づいて、メモリ内`CRuntimeClass`以前格納アーカイブして、ファイルに書き込む情報。  
  
 したがって、かどうかを使用する、 `CArchive`  **< \<** と **>>** 演算子を呼び出すと`Serialize`、かどうかに依存する*必要*オブジェクトを動的に再構築に読み込みを行うアーカイブに基づいて以前に保存された`CRuntimeClass`情報。 使用して、`Serialize`関数は、次の場合。  
  
-   オブジェクトを逆シリアル化するときに事前にわかっているオブジェクトの正確なクラスです。  
  
-   オブジェクトを逆シリアル化するときに、それに割り当てられたメモリがあります。  
  
> [!CAUTION]
>  使用してオブジェクトを読み込む場合、`Serialize`関数を使用してオブジェクトを格納する必要がありますも、`Serialize`関数。 使用して保存しないで、 `CArchive`  **<<** 演算子と、ロードを使用して、`Serialize`関数、またはを使用してストア、`Serialize`関数を使用して、読み込み**CArchive >>**演算子。  
  
 次の例では、ケースを示します。  
  
 [!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]  
  
 [!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]  
  
 要約すると、埋め込まれたシリアル化可能なクラスが定義されている場合に**CObjec**メンバーとして t、する必要があります*いない*を使用して、 `CArchive`  **< \<** および **>>** 演算子、そのオブジェクトを呼び出す必要がありますが、`Serialize`関数を使用します。 また、シリアル化可能なクラスへのポインターを定義する場合、 `CObject` (から派生したオブジェクトまたは`CObject`) が、メンバー、コンストラクトとしてこの他のオブジェクトに独自のコンス トラクターで呼び出す必要もあります`Serialize`です。  
  
## <a name="see-also"></a>参照  
 [シリアル化: オブジェクトのシリアル化](../mfc/serialization-serializing-an-object.md)

