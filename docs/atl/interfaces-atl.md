---
title: "インターフェイス (ATL) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bf1dd68a3ca8e6735b07c5bd7247b457bd7d246d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="interfaces-atl"></a>インターフェイス (ATL)
インターフェイスは、オブジェクトが外部への機能を公開する方法です。 COM では、インターフェイスは、(C++ vtable) のようなオブジェクトによって実装されている関数へのポインターのテーブルです。 テーブルは、インターフェイスを表し、指す関数は、そのインターフェイスのメソッド。 オブジェクトは、選択され、同数のインターフェイスを公開できます。  
  
 各インターフェイスは、基本的な COM インターフェイスに基づいて[IUnknown](../atl/iunknown.md)です。 メソッド**IUnknown**オブジェクトによって公開されるその他のインターフェイスに移動できます。  
  
 また、各インターフェイスには、一意のインターフェイス ID (IID) が与えられます。 この一意性しやすいインターフェイスのバージョン管理をサポートします。 インターフェイスの新しいバージョンは、新しい IID を持つ、新しいインターフェイスだけです。  
  
> [!NOTE]
>  標準の COM と OLE インターフェイスの Iid が定義されています。  
  
## <a name="see-also"></a>参照  
 [COM の概要](../atl/introduction-to-com.md)   
 [COM オブジェクトとインターフェイス](http://msdn.microsoft.com/library/windows/desktop/ms690343)

