---
title: "CAtlServiceModuleT::ServiceMain 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ServiceMain
- CServiceModule::ServiceMain
- CServiceModule.ServiceMain
dev_langs:
- C++
helpviewer_keywords:
- ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 633e9bc4689ced93e1c22151b32654f7ae9d7ece
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="catlservicemoduletservicemain-function"></a>CAtlServiceModuleT::ServiceMain 関数
サービス コントロール マネージャー (SCM) を呼び出す`ServiceMain`コントロール パネルの サービス アプリケーションを開いたときに、サービスを選択し、をクリックして**開始**です。  
  
 SCM 後、呼び出して`ServiceMain`サービスがハンドラー関数には、SCM の与える必要があります。 この関数は、サービスの状態を取得して (一時停止または停止) などの具体的な手順を渡す SCM を使用できます。 SCM は、サービスが成功したときにこの関数を取得**_Handler** Win32 API 関数を[RegisterServiceCtrlHandler](http://msdn.microsoft.com/library/windows/desktop/ms685054)です。 (**_Handler**非静的メンバー関数を呼び出す静的メンバー関数は、[ハンドラー](../atl/reference/catlservicemodulet-class.md#handler))。  
  
 起動時に、サービスは、現在の状態の SCM を通知する必要もします。 これは渡すことによって、 **SERVICE_START_PENDING** Win32 API 関数を[SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241)です。  
  
 `ServiceMain`呼び出して`CAtlExeModuleT::InitializeCom`、Win32 API 関数を呼び出している[CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279)です。 既定では、`InitializeCom`渡します、 **COINIT_MULTITHREADED**関数へのフラグ。 このフラグは、プログラムがフリー スレッドのサーバーであることを示します。  
  
 ここで、`CAtlServiceModuleT::Run`サービスの主な作業を実行すると呼びます。 **実行**サービスが停止されるまでの実行を継続します。  
  
## <a name="see-also"></a>参照  
 [サービス](../atl/atl-services.md)   
 [CAtlServiceModuleT::ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)

