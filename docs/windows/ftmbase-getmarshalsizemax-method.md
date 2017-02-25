---
title: "FtmBase::GetMarshalSizeMax メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase::GetMarshalSizeMax"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetMarshalSizeMax メソッド"
ms.assetid: b416b1bf-c73e-45d5-abb8-04921c1a0c94
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# FtmBase::GetMarshalSizeMax メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定されたオブジェクトの指定されたインターフェイス ポインターをマーシャリングするために必要なバイト数の上限を取得します。  
  
## 構文  
  
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
  
#### パラメーター  
 `riid`  
 マーシャリングされる必要インターフェイスの識別子への参照。  
  
 `pv`  
 マーシャリングされる;インターフェイス ポインター。NULL の場合もあります。  
  
 `dwDestContext`  
 指定されたインターフェイスがマーシャリングを解除される前のコンテキスト。  
  
 一つ以上の MSHCTX の列挙値を指定します。  
  
 現在、マーシャリングを解除するには、現在のプロセス \(MSHCTX\_LOCAL\) と現在のプロセス \(MSHCTX\_INPROC\) の別のアパートメントにまたは同じコンピューター上の他のプロセスに発生します。  
  
 `pvDestContext`  
 将来使用するために予約されて; NULL である必要があります。  
  
 `mshlflags`  
 データがクライアント プロセス—一般的なケース \(が送信されることも、複数のクライアントによって取得するできるグローバル テーブルに書き込まれる必要があるマーシャリングされるかどうかを示すためにフラグを設定します。  一つ以上の MSHLFLAGS の列挙値を指定します。  
  
 `pSize`  
 この操作が完了すると、マーシャリングのストリームに書き込むデータの容量の上限へのポインター。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は E\_FAIL または E\_NOINTERFACE。  
  
## 必要条件  
 **ヘッダー:** ftm.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [FtmBase クラス](../windows/ftmbase-class.md)