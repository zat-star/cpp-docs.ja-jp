---
title: "CAtlServiceModuleT::Handler 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CServiceModule::Handler
- CServiceModule.Handler
- Handler
dev_langs: C++
helpviewer_keywords: Handler method
ms.assetid: 14db5f2a-be87-4774-a296-445cb6fc7b2e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9f8c83db3f7834c79656adc3443fd3c8946a4176
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="catlservicemodulethandler-function"></a>CAtlServiceModuleT::Handler 関数
`CAtlServiceModuleT::Handler`サービス コントロール マネージャー (SCM) 呼び出し、サービスの状態を取得し、(停止または一時停止) などのさまざまな指示を付けますルーチンです。 SCM を操作するコードを渡します`Handler`を示す、サービスが行う必要があります。 既定の ATL で生成されたサービスは、stop 命令を処理するのみです。 SCM には、stop 命令が成功した場合、サービスは、プログラムを停止するが、SCM を指示します。 サービスを呼び出すし`PostThreadMessage`自体に終了メッセージを送信します。 メッセージ ループを終了このし、サービスが最終的に終了します。  
  
 詳細については、処理を変更する必要があります、`m_status`データ メンバーの初期化で、`CAtlServiceModuleT`コンス トラクターです。 このデータ メンバーは、サービスが、コントロール パネルの サービス アプリケーションで選択したときに有効にするボタン、SCM を指示します。  
  
## <a name="see-also"></a>関連項目  
 [サービス](../atl/atl-services.md)   
 [CAtlServiceModuleT::Handler](../atl/reference/catlservicemodulet-class.md#handler)

