---
title: "Ftmbase::marshalinterface メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: ftm/Microsoft::WRL::FtmBase::MarshalInterface
dev_langs: C++
helpviewer_keywords: MarshalInterface method
ms.assetid: fc8421b4-06e4-4925-b908-c285fe4790d2
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9df1e5d7559b434c1af0f1feff3b73b8141a8865
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ftmbasemarshalinterface-method"></a>FtmBase::MarshalInterface メソッド
一部のクライアント プロセスで、プロキシ オブジェクトを初期化するために必要なデータをストリームに書き込みます。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHODIMP MarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags  
) override;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pStm`  
 マーシャ リング中に使用するストリームへのポインター。  
  
 `riid`  
 マーシャ リングするインターフェイスの識別子への参照。 このインターフェイスは IUnknown インターフェイスから派生する必要があります。  
  
 `pv`  
 マーシャ リング; へのインターフェイス ポインターへのポインター呼び出し元では、目的のインターフェイスには、ポインターにいない場合、NULL を指定できます。  
  
 `dwDestContext`  
 移行先コンテキストで指定されたインターフェイスのマーシャ リングします。  
  
 1 つまたは複数の MSHCTX 列挙値を指定します。  
  
 マーシャ リング解除 (MSHCTX_INPROC) 現在のプロセスの別のアパートメントまたは現在のプロセス (MSHCTX_LOCAL) と同じコンピューター上の別のプロセスで発生します。  
  
 `pvDestContext`  
 今後使用するために予約されています。0 にする必要があります。  
  
 `mshlflags`  
 マーシャ リングするデータが、クライアントのプロセスに送信されるかどうかを指定します: 一般的な事例 — または複数のクライアントで取得できる、グローバル テーブルに書き込まれます。  
  
## <a name="return-value"></a>戻り値  
 S_OK  
 インターフェイス ポインターが正常にマーシャ リングします。  
  
 E_NOINTERFACE  
 指定されたインターフェイスがサポートされていません。  
  
 STG_E_MEDIUMFULL  
 ストリームがいっぱいです。  
  
 E_FAIL  
 操作に失敗しました。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** ftm.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [FtmBase クラス](../windows/ftmbase-class.md)