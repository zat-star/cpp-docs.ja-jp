---
title: "主要な関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CServiceModule::Run
- CServiceModule.Run
- CSecurityDescriptor
dev_langs: C++
helpviewer_keywords: ATL services, security
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 383b054314982a0828d51083a904ccb2f7ddb5d5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="catlservicemoduletrun-function"></a>主要な関数
**実行**の呼び出しを含む`PreMessageLoop`、 `RunMessageLoop`、および`PostMessageLoop`です。 呼び出される後`PreMessageLoop`最初に、サービスのスレッドの ID を格納します サービスは、この ID を使用して送信することでそれ自体を閉じるには、 **WM_QUIT** Win32 API 関数を使用してメッセージ[次](http://msdn.microsoft.com/library/windows/desktop/ms644946)です。  
  
 `PreMessageLoop`呼び出して`InitializeSecurity`です。 既定では、`InitializeSecurity`呼び出し[CoInitializeSecurity](http://msdn.microsoft.com/library/windows/desktop/ms693736)を NULL に設定するセキュリティ記述子、つまり、ユーザーが、オブジェクトへのアクセスを持っています。  
  
 サービスを独自のセキュリティを指定したくない場合は上書き`PreMessageLoop`を呼び出さないと`InitializeSecurity`COM は、レジストリからのセキュリティ設定を確認します。 レジストリ設定を構成する便利な方法は、 [DCOMCNFG](../atl/dcomcnfg.md)ユーティリティのこのセクションで後ほど説明します。  
  
 セキュリティを指定すると、新しいクライアントがプログラムに接続できるようにを COM オブジェクトが登録します。 最後に、プログラムが実行されていることと、プログラムがメッセージ ループに入り、サービス コントロール マネージャー (SCM) に指示します。 サービスのシャット ダウン時に終了メッセージを送信するまで、プログラムを実行したままです。  
  
## <a name="see-also"></a>関連項目  
 [サービス](../atl/atl-services.md)   
 [CSecurityDesc クラス](../atl/reference/csecuritydesc-class.md)   
 [CSid クラス](../atl/reference/csid-class.md)   
 [CDacl クラス](../atl/reference/cdacl-class.md)   
 [主要な](../atl/reference/catlservicemodulet-class.md#run)

