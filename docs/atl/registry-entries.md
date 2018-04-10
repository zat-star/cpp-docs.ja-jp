---
title: レジストリ エントリ (ATL) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- registry, ATL services entries
- registry, application IDs
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: faef0ca0c1c9c4c2986a039b8b1a26517641acd0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="registry-entries"></a>レジストリ エントリ
DCOM では、アプリケーション Id (Appid)、レジストリで一元的な場所に 1 つまたは複数の DCOM オブジェクトの構成オプションをグループ化の概念が導入されました。 AppID を指定するには、名前付きの下にあるオブジェクトの CLSID 値 AppID の値を示すです。  
  
 既定では、ATL で生成されたサービスは GUID と、CLSID は、AppID を使用します。  `HKEY_CLASSES_ROOT\AppID`DCOM に固有のエントリを指定することができます。 最初に、2 つのエントリが存在します。  
  
-   `LocalService`、、サービスの名前と同じ値を使用します。 この値が存在する場合は、代わりに使用、 `LocalServer32` CLSID の下にあるキー。  
  
-   `ServiceParameters`に等しい値を持つ`-Service`します。 この値は、起動したときにサービスに渡されるパラメーターを指定します。 これらのパラメーターは、サービスに渡される注`ServiceMain`機能しない`WinMain`です。  
  
 DCOM サービスも下にある別のキーを作成する必要があります`HKEY_CLASSES_ROOT\AppID`です。 このキーがの exe ファイルの名前と同じと AppID のエントリを指す AppID 値が含まれている、相互参照として機能します。  
  
## <a name="see-also"></a>参照  
 [サービス](../atl/atl-services.md)

