---
title: "CKeyFrame クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CKeyFrame"
  - "CKeyFrame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CKeyFrame クラス"
ms.assetid: d050a562-20f6-4c65-8ce5-ccb3aef1a20e
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CKeyFrame クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アニメーションのキーフレームを表します。  
  
## 構文  
  
```  
class CKeyFrame : public CBaseKeyFrame;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CKeyFrame::CKeyFrame](../Topic/CKeyFrame::CKeyFrame.md)|オーバーロードされます。  他のキーフレームに依存するキーフレームを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CKeyFrame::AddToStoryboard](../Topic/CKeyFrame::AddToStoryboard.md)|ストーリーボードにキーフレームを追加します   \([CBaseKeyFrame::AddToStoryboard](../Topic/CBaseKeyFrame::AddToStoryboard.md) をオーバーライドします\)。|  
|[CKeyFrame::AddToStoryboardAfterTransition](../Topic/CKeyFrame::AddToStoryboardAfterTransition.md)|キーフレームをストーリーボード内の遷移後に追加します。|  
|[CKeyFrame::AddToStoryboardAtOffset](../Topic/CKeyFrame::AddToStoryboardAtOffset.md)|キーフレームをストーリーボード内のオフセット位置に追加します。|  
|[CKeyFrame::GetExistingKeyframe](../Topic/CKeyFrame::GetExistingKeyframe.md)|このキーフレームが依存するキーフレームへのポインターを返します。|  
|[CKeyFrame::GetOffset](../Topic/CKeyFrame::GetOffset.md)|他のキーフレームからのオフセットを返します。|  
|[CKeyFrame::GetTransition](../Topic/CKeyFrame::GetTransition.md)|このキーフレームが依存する遷移へのポインターを返します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CKeyFrame::m\_offset](../Topic/CKeyFrame::m_offset.md)|m\_pExistingKeyFrame に格納されているキーフレームからのこのキーフレームのオフセットを指定します。|  
|[CKeyFrame::m\_pExistingKeyFrame](../Topic/CKeyFrame::m_pExistingKeyFrame.md)|既存のキーフレームへのポインターを格納します。  このキーフレームは、ストーリーボード内で既存のキーフレームから m\_offset の位置に追加されます。|  
|[CKeyFrame::m\_pTransition](../Topic/CKeyFrame::m_pTransition.md)|このキーフレームから開始される遷移へのポインターを格納します。|  
  
## 解説  
 このクラスは、アニメーションのキーフレームを実装します。  キーフレームはストーリーボード内の特定の時点を表し、遷移の開始時間と終了時間を指定するために使用できます。  キーフレームは、他のキーフレームを基準にそのキーフレームからのオフセット \(秒\) を持つ場合と、遷移を基準にその遷移の終了時間を表す場合があります。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CBaseKeyFrame](../Topic/CBaseKeyFrame%20Class.md)  
  
 [CKeyFrame](../../mfc/reference/ckeyframe-class.md)  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)