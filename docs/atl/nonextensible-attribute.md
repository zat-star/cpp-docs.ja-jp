---
title: "nonextensible 属性 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: nonextensible
dev_langs: C++
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: af16748bb3b2048ce854ccc7a03b2400039184a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="nonextensible-attribute"></a>nonextensible 属性
かどうかは、デュアル インターフェイスは実行時に拡張できません (つまり、メソッドまたはプロパティ経由で提供されません**idispatch::invoke**を利用できない、vtable を使用して)、適用する必要があります、 **nonextensible**インターフェイス定義する属性します。 この属性は、コンパイル時に完全なコードの検証を有効にするために使用する (Visual Basic の場合) などのクライアント言語に情報を提供します。 この属性が指定されていない場合バグが非表示のままクライアント コードで実行時までです。  
  
 詳細については、 **nonextensible**属性と例を参照してください[nonextensible](../windows/nonextensible.md)です。  
  
## <a name="see-also"></a>参照  
 [デュアル インターフェイスと ATL](../atl/dual-interfaces-and-atl.md)

