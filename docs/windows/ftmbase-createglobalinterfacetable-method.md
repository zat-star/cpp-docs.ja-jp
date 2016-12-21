---
title: "FtmBase::CreateGlobalInterfaceTable メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase::CreateGlobalInterfaceTable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateGlobalInterfaceTable メソッド"
ms.assetid: bb82a0c5-22b9-4844-9204-7922033d8b07
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# FtmBase::CreateGlobalInterfaceTable メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

グローバル インターフェイス テーブル \(GIT\) を作成します。  
  
## 構文  
  
```  
static HRESULT CreateGlobalInterfaceTable(  
   __out IGlobalInterfaceTable **git  
);  
```  
  
#### パラメーター  
 `git`  
 この操作が完了すると、グローバル インターフェイス テーブルへのポインター。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は、エラーを示す HRESULT を返します。  
  
## 解説  
 詳細については、MSDN ライブラリの「COM 「IGlobalInterfaceTable」を」COM インターフェイス ポインターのサブトピックを参照して」トピックを参照します。  
  
## 必要条件  
 **ヘッダー:** ftm.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [FtmBase クラス](../windows/ftmbase-class.md)