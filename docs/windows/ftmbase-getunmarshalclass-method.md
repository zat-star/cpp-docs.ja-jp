---
title: "FtmBase::GetUnmarshalClass メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetUnmarshalClass メソッド"
ms.assetid: 535fc539-5b97-4967-b158-f7568f13d341
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# FtmBase::GetUnmarshalClass メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

対応するプロキシのコードを含む DLL を検索するときに COM を使用する CLSID を取得します。  COM は、プロキシの初期化されていないインスタンスを作成するには、この DLL を読み込みます。  
  
## 構文  
  
```  
STDMETHODIMP GetUnmarshalClass(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out CLSID *pCid  
) override;  
```  
  
#### パラメーター  
 `riid`  
 マーシャリングされる必要インターフェイスの識別子への参照。  
  
 `pv`  
 マーシャリングされる;インターフェイスへのポインター。呼び出し元が指定したインターフェイスへのポインターが NULL でも指定できます。  
  
 `dwDestContext`  
 指定されたインターフェイスがマーシャリングを解除される前のコンテキスト。  
  
 一つ以上の MSHCTX の列挙値を指定します。  
  
 マーシャリング解除は現在のプロセス \(MSHCTX\_LOCAL\) と現在のプロセス \(MSHCTX\_INPROC\) の別のアパートメントにまたは同じコンピューター上の他のプロセスに発生します。  
  
 `pvDestContext`  
 将来使用するために予約されて; NULL である必要があります。  
  
 `mshlflags`  
 この操作が完了すると、クライアント プロセス内のプロキシを作成するために使用される CLSID へのポインター。  
  
 `pCid`  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は S\_FALSE。  
  
## 必要条件  
 **ヘッダー:** ftm.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [FtmBase クラス](../windows/ftmbase-class.md)