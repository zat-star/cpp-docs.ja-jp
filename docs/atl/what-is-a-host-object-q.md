---
title: "ホスト オブジェクトとは何ですか。 (ATL) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- host objects
ms.assetid: 4f8da992-b27e-45e8-b5e0-c8b1dcae4fac
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: da735caa84c133b9cdf63fae5df8bdd3d5f774b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="what-is-a-host-object"></a>ホスト オブジェクトとは何ですか。
ホスト オブジェクトは、ATL で特定のウィンドウに指定された ActiveX コントロール コンテナーを表す COM オブジェクトです。 ホスト オブジェクトはサブクラス コンテナー ウィンドウ コントロールにメッセージを反映したものをようにコントロールで使用するために必要なコンテナー インターフェイスを提供し、公開、 [IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md)と[IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md)コントロールの環境を構成できるようにするインターフェイスです。  
  
 ホスト オブジェクトを使用して、コンテナーのアンビエント プロパティを設定することができます。  
  
## <a name="see-also"></a>参照  
 [コントロール コンテインメントよく寄せられる質問](../atl/atl-control-containment-faq.md)

