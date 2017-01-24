---
title: "CAsyncMonikerFile クラス | Microsoft Docs"
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
  - "CAsyncMonikerFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX コントロール [C++], 非同期"
  - "非同期コントロール [C++]"
  - "CAsyncMonikerFile クラス"
  - "IMoniker インターフェイス, バインド"
  - "モニカー [C++], MFC"
  - "OLE コントロール [C++], 非同期"
ms.assetid: 17378b66-a49a-4b67-88e3-7756ad26a2fc
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAsyncMonikerFile クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ActiveX コントロール \(以前の OLE コントロール\) で非同期モニカーを使用するための機能が用意されています。  
  
## 構文  
  
```  
class CAsyncMonikerFile : public CMonikerFile  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAsyncMonikerFile::CAsyncMonikerFile](../Topic/CAsyncMonikerFile::CAsyncMonikerFile.md)|`CAsyncMonikerFile` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAsyncMonikerFile::Close](../Topic/CAsyncMonikerFile::Close.md)|すべてのリソースを閉じ、解放します。|  
|[CAsyncMonikerFile::GetBinding](../Topic/CAsyncMonikerFile::GetBinding.md)|非同期束縛のコピーへのポインターを取得します。|  
|[CAsyncMonikerFile::GetFormatEtc](../Topic/CAsyncMonikerFile::GetFormatEtc.md)|ストリームのデータ形式を取得します。|  
|[CAsyncMonikerFile::Open](../Topic/CAsyncMonikerFile::Open.md)|ファイルを非同期的に開きます。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAsyncMonikerFile::CreateBindStatusCallback](../Topic/CAsyncMonikerFile::CreateBindStatusCallback.md)|COM オブジェクトを実装する `IBindStatusCallback`作成します。|  
|[CAsyncMonikerFile::GetBindInfo](../Topic/CAsyncMonikerFile::GetBindInfo.md)|バインドの型情報を作成することを要求するために、OLE システム ライブラリによって呼び出されます。|  
|[CAsyncMonikerFile::GetPriority](../Topic/CAsyncMonikerFile::GetPriority.md)|バインディングの優先順位を取得するために、OLE システム ライブラリによって呼び出されます。|  
|[CAsyncMonikerFile::OnDataAvailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md)|これは非同期バインド操作中にクライアントで使用可能になるようにデータを提供するために呼び出されます。|  
|[CAsyncMonikerFile::OnLowResource](../Topic/CAsyncMonikerFile::OnLowResource.md)|リソースが少ないときに呼び出されます。|  
|[CAsyncMonikerFile::OnProgress](../Topic/CAsyncMonikerFile::OnProgress.md)|データをダウンロードする処理の進行状況を示すために呼び出されます。|  
|[CAsyncMonikerFile::OnStartBinding](../Topic/CAsyncMonikerFile::OnStartBinding.md)|バインディングの起動になるときに呼び出されます。|  
|[CAsyncMonikerFile::OnStopBinding](../Topic/CAsyncMonikerFile::OnStopBinding.md)|非同期コピーが停止すると呼び出されます。|  
  
## 解説  
 [CMonikerFile](../Topic/CMonikerFile%20Class.md)から派生した、[COleStreamFile](../Topic/COleStreamFile%20Class.md)から派生した、`CAsyncMonikerFile` は、URL からの読み込みのファイルを含むデータ ストリームを非同期にアクセスするために [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) のインターフェイスを非同期的に使用します。  ファイルは ActiveX コントロールの datapath のプロパティです。  
  
 非同期モニカーは、インターネット対応アプリケーションと ActiveX コントロールで主にファイル転送中に依存したユーザー インターフェイスを提供するために使用されます。  このの最も良い例は、ActiveX コントロールに非同期プロパティを提供する [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) の使用です。  `CDataPathProperty` のオブジェクトは、長い所持品の交換処理中に新しいデータを使用できるかどうかを示すためにコールバックを取得します。  
  
 インターネット アプリケーションで非同期モニカーと ActiveX コントロールを使用する方法の詳細については、次のトピックを参照:  
  
-   [インターネットの対処方法: 非同期モニカー](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
-   [インターネットの対処方法: &#91;ActiveX コントロール&#93;](../../mfc/activex-controls-on-the-internet.md)  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../Topic/COleStreamFile%20Class.md)  
  
 [CMonikerFile](../Topic/CMonikerFile%20Class.md)  
  
 `CAsyncMonikerFile`  
  
## 必要条件  
 **Header:** afxole.h  
  
## 参照  
 [CMonikerFile クラス](../Topic/CMonikerFile%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CMonikerFile クラス](../Topic/CMonikerFile%20Class.md)   
 [CDataPathProperty クラス](../../mfc/reference/cdatapathproperty-class.md)   
 [Asynchronous Versus Synchronous Monikers](http://msdn.microsoft.com/library/windows/desktop/ms687193)