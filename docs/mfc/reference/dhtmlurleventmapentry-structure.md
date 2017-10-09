---
title: "DHtmlUrlEventMapEntry 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DHtmlUrlEventMapEntry
dev_langs:
- C++
helpviewer_keywords:
- DHtmlUrlEventMapEntry structure [MFC]
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 37e43514c116f93841b1479103a6f29ec708bfa0
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="dhtmlurleventmapentry-structure"></a>DHtmlUrlEventMapEntry 構造体
`DHtmlUrlEventMapEntry`構造はマルチ URL イベント マップのサポートを提供します。  
  
## <a name="syntax"></a>構文  
  
```  
struct DHtmlUrlEventMapEntry  
{  
LPCTSTR szUrl;  
const DHtmlEventMapEntry *pEventMap;  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 `szUrl`  
 URL です。  
  
 *pEventMap*  
 URL に関連付けられているイベント マップします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdhtml.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)


