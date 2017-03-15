---
title: "SRWLock クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::SRWLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SRWLock クラス"
ms.assetid: 4fa250e3-5f29-4b06-ac24-61b6c04ade93
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# SRWLock クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

スリム リーダー\/ライター ロックを表します。  
  
## 構文  
  
```  
class SRWLock;  
```  
  
## 解説  
 スリム リーダーとライター ロックとはスレッド間でリソースへのアクセスを同期するために使用されます。  詳細については、MSDN ライブラリの [同期関数](http://msdn.microsoft.com/ja-jp/9b6359c2-0113-49b6-83d0-316ad95aba1b) を参照します。  
  
## メンバー  
  
### パブリック typedef  
  
|||  
|-|-|  
|**SyncLockExclusive**|排他モードで取得した SRWLock オブジェクトのシノニムです。|  
|**SyncLockShared**|共有モードで取得した SRWLock オブジェクトのシノニムです。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[SRWLock::SRWLock コンストラクター](../windows/srwlock-srwlock-constructor.md)|SRWLock クラスの新しいインスタンスを初期化します。|  
|[SRWLock::~SRWLock デストラクター](../windows/srwlock-tilde-srwlock-destructor.md)|Deinitializes SRWLock クラスのインスタンス。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[SRWLock::LockExclusive メソッド](../windows/srwlock-lockexclusive-method.md)|排他モードの SRWLock オブジェクトを取得します。|  
|[SRWLock::LockShared メソッド](../windows/srwlock-lockshared-method.md)|共有モードの SRWLock オブジェクトを取得します。|  
|[SRWLock::TryLockExclusive メソッド](../windows/srwlock-trylockexclusive-method.md)|SRWLock の現在のディレクトリまたは指定オブジェクトの排他モードの SRWLock オブジェクトを取得しようとします。|  
|[SRWLock::TryLockShared メソッド](../windows/srwlock-trylockshared-method.md)|SRWLock の現在のディレクトリまたは指定オブジェクトの共有モードの SRWLock オブジェクトを取得しようとします。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[SRWLock::SRWLock\_ データ メンバー](../windows/srwlock-srwlock-data-member.md)|SRWLock の現在のオブジェクトの基になるロック変数も含まれます。|  
  
## 継承階層  
 `SRWLock`  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [Microsoft::WRL::Wrappers 名前空間](../Topic/Microsoft::WRL::Wrappers%20Namespace.md)