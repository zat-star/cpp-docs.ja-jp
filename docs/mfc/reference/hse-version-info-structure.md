---
title: "HSE_VERSION_INFO 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: HSE_VERSION_INFO
dev_langs: C++
helpviewer_keywords: HSE_VERSION_INFO structure [MFC]
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 108f826ffaa17de65dafe246ab6724fac2b134f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="hseversioninfo-structure"></a>HSE_VERSION_INFO 構造体
この構造体を指す、`pVer`内のパラメーター、`CHttpServer::GetExtensionVersion`メンバー関数。 ISA のバージョン番号と、ISA のテキストの説明を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct _HSE_VERSION_INFO {  
    DWORD dwExtensionVersion;  
    CHAR lpszExtensionDesc[HSE_MAX_EXT_DLL_NAME_LEN];  
} HSE_VERSION_INFO, *LPHSE_VERSION_INFO;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *dwExtensionVersion*  
 ISA のバージョン番号  
  
 *lpszExtensionDesc*  
 ISA のテキストの説明 既定の実装は、プレース ホルダー テキストです。オーバーライド`CHttpServer::GetExtensionVersion`に独自の説明を提供します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** httpext.h  
  
## <a name="see-also"></a>参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

