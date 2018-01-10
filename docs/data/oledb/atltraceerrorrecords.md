---
title: "AtlTraceErrorRecords |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.AtlTraceErrorRecords
- ATL::AtlTraceErrorRecords
- AtlTraceErrorRecords
dev_langs: C++
helpviewer_keywords: AtlTraceErrorRecords function
ms.assetid: b83970b3-dc2a-445c-9142-f52218719905
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4a3f8542f2c897f45916ac62fbac147259b2362d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="atltraceerrorrecords"></a>AtlTraceErrorRecords
エラーが返された場合は、ダンプ デバイスに OLE DB エラー レコード情報をダンプします。  
  
## <a name="syntax"></a>構文  
  
```  
  
      inline void AtlTraceErrorRecords(   
   HRESULT hrErr = S_OK    
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hErr`  
 [in]`HRESULT` OLE DB コンシューマー テンプレート メンバー関数によって返されます。  
  
## <a name="remarks"></a>コメント  
 場合`hErr`は`S_OK`、`AtlTraceErrorRecords`ダンプの OLE DB エラー レコード情報をダンプ デバイス (、**デバッグ**ファイルまたは出力ウィンドウのタブ)。 エラー レコードについてには、プロバイダーから取得されるには、各エラー レコード エントリの行番号、ソース、説明、ヘルプ ファイルをコンテキスト、および GUID が含まれます。 `AtlTraceErrorRecords`デバッグ ビルドでのみこの情報をダンプします。 リリース ビルドでは、out に最適化された空のスタブを勧めします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [マクロと OLE DB コンシューマー テンプレート用グローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [CDBErrorInfo クラス](../../data/oledb/cdberrorinfo-class.md)