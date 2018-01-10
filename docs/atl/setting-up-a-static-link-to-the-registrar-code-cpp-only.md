---
title: "レジストラー コード (C++ のみ) への静的リンクの設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- statically linking to ATL Registrar code
- linking [C++], to ATL Registrar code
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d49ed2a56738ec784c8a1a2cc3c13239f7317270
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>レジストラー コード (C++ のみ) への静的リンクを設定します。
C++ のクライアントは、レジストラーのコードに静的なリンクを作成できます。 リリース ビルドを約 5 K を追加、レジストラーのパーサーの静的にリンクします。  
  
 静的リンクを設定する最も簡単な方法は、指定した前提としています。[代入](reference/registry-macros.md#declare_registry_resourceid)オブジェクトの宣言でします。 (これは、ATL で使用される既定の指定)  
  
### <a name="to-create-a-static-link-using-declareregistryresourceid"></a>代入を使用して静的なリンクを作成するには  
  
1.  指定[/D](../build/reference/d-preprocessor-definitions.md) `_ATL_STATIC_REGISTRY` /D ではなく**_ATL_DLL**です。  
  
2.  再コンパイルします。  
  
## <a name="see-also"></a>参照  
 [レジストリ コンポーネント (レジストラー)](../atl/atl-registry-component-registrar.md)

