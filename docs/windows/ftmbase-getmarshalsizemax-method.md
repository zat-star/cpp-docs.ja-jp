---
title: "Ftmbase::getmarshalsizemax メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: ftm/Microsoft::WRL::FtmBase::GetMarshalSizeMax
dev_langs: C++
helpviewer_keywords: GetMarshalSizeMax method
ms.assetid: b416b1bf-c73e-45d5-abb8-04921c1a0c94
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0d68889531c270db190f861eb20a34783b88987f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ftmbasegetmarshalsizemax-method"></a>FtmBase::GetMarshalSizeMax メソッド
指定したオブジェクトの指定されたインターフェイス ポインターをマーシャ リングするために必要なバイト数の上限値を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHODIMP GetMarshalSizeMax(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out DWORD *pSize  
) override;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `riid`  
 マーシャ リングするインターフェイスの識別子への参照。  
  
 `pv`  
 インターフェイス ポインターをマーシャ リングします。NULL にすることができます。  
  
 `dwDestContext`  
 移行先コンテキストで指定されたインターフェイスのマーシャ リングします。  
  
 1 つまたは複数の MSHCTX 列挙値を指定します。  
  
 現時点では、マーシャ リング解除行える (MSHCTX_INPROC) 現在のプロセスの別のアパートメントまたは現在のプロセス (MSHCTX_LOCAL) と同じコンピューター上の別のプロセスです。  
  
 `pvDestContext`  
 将来使用するために予約されていますNULL にする必要があります。  
  
 `mshlflags`  
 マーシャ リングするデータが、クライアントのプロセスに送信されるかどうかを示すフラグ: 一般的な事例 — または複数のクライアントで取得できる、グローバル テーブルに書き込まれます。 1 つまたは複数の MSHLFLAGS 列挙値を指定します。  
  
 `pSize`  
 この操作の完了時、マーシャ リングのストリームに書き込まれるデータの量に上限の境界へのポインター。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK、それ以外の場合、E_FAIL または E_NOINTERFACE します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** ftm.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [FtmBase クラス](../windows/ftmbase-class.md)