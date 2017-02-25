---
title: "CAnimateCtrl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAnimateCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アニメーション コントロール [C++], CAnimateCtrl クラス"
  - "CAnimateCtrl クラス"
  - "Windows コモン コントロール [C++], CAnimateCtrl クラス"
ms.assetid: 5e8eb1bd-96b7-47b8-8de2-6bcbb3cc299b
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CAnimateCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows コモン アニメーション コントロールの機能が用意されています。  
  
## 構文  
  
```  
  
class CAnimateCtrl : public CWnd  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAnimateCtrl::CAnimateCtrl](../Topic/CAnimateCtrl::CAnimateCtrl.md)|`CAnimateCtrl` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAnimateCtrl::Close](../Topic/CAnimateCtrl::Close.md)|AVI のクリッピングを閉じます。|  
|[CAnimateCtrl::Create](../Topic/CAnimateCtrl::Create.md)|アニメーションのコントロールを作成し、`CAnimateCtrl` のオブジェクトにアタッチします。|  
|[CAnimateCtrl::CreateEx](../Topic/CAnimateCtrl::CreateEx.md)|指定されたウィンドウの拡張スタイルのアニメーション コントロールを作成し、`CAnimateCtrl` のオブジェクトにアタッチします。|  
|[CAnimateCtrl::IsPlaying](../Topic/CAnimateCtrl::IsPlaying.md)|Audio Video Interleaved \(AVI\) のクリッピングが再生中かどうかを示します。|  
|[CAnimateCtrl::Open](../Topic/CAnimateCtrl::Open.md)|ファイルまたはリソースから AVI のクリッピングを開き、最初のフレームを表示します。|  
|[CAnimateCtrl::Play](../Topic/CAnimateCtrl::Play.md)|サウンドなしで AVI のをクリップします。|  
|[CAnimateCtrl::Seek](../Topic/CAnimateCtrl::Seek.md)|AVI のクリップ選択した一つのフレームを表示します。|  
|[CAnimateCtrl::Stop](../Topic/CAnimateCtrl::Stop.md)|AVI のクリッピングを停止します。|  
  
## 解説  
 このコントロール \(したがって `CAnimateCtrl` のクラス\) Windows 95、Windows 98、および Windows NT 3.51 以降で実行されるプログラムにのみ使用できます。  
  
 アニメーション コントロールは AVI \(Audio Video Interleaved\) 形式のいずれを Windows 標準的なビデオとオーディオ形式表示する四角形ウィンドウです。  AVI のクリッピングはムービーのような一連のビットマップ フレームです。  
  
 アニメーション コントロールは、単純な AVI のクリッピングのみ行うことができます。  具体的には、アニメーション コントロールが遊ばれるクリップは、次の条件を満たす必要があります:  
  
-   、1 桁のビデオ ストリームがない場合、少なくとも 1 フレームが必要です。  
  
-   アニメーション コントロールがオーディオ情報は無視されます\) がファイルに最大 2 ビットのストリームがあります \(通常は他のストリームが存在する場合、オーディオ ストリームです。  
  
-   クリッピングは RLE8 と圧縮解除されていないかまたは圧縮する必要があります。  
  
-   ビデオ ストリームのパレットの変更は使用できません。  
  
 AVI のリソースとしてアプリケーションに AVI のクリッピングを追加することも、別の AVI ファイルとしてアプリケーションに付随することができます。  
  
 AVI のクリッピングが表示されている間、スレッドが実行を続けるため、アニメーション コントロールの 1 とおりの使用がかかる操作中にシステム アクティビティを示すことです。  たとえば、ファイル エクスプローラーの\[検索\]ダイアログ ボックスでは、システムがファイルを検索するときに移動拡大鏡を表示します。  
  
 ダイアログ エディターを使用してダイアログ ボックスまたはダイアログ内のリソースの `CAnimateCtrl` のオブジェクトを作成し、ユーザーがダイアログ ボックスを閉じると、自動的に破棄されます。  
  
 ウィンドウ内の `CAnimateCtrl` のオブジェクトを作成する場合は、オブジェクトを破棄する必要があります。  `CAnimateCtrl` オブジェクトをスタック上に作成したときは、自動的に破棄されます。  **new** 関数を使ってヒープ領域の `CAnimateCtrl` のオブジェクトを作成する場合は、オブジェクトを破棄するオブジェクトの **\[削除\]** を呼び出す必要があります。  `CAnimateCtrl` から新しいクラスを派生し、そのクラスのメモリを割り当てた場合、割り当てを破棄するに `CAnimateCtrl` のデストラクターをオーバーライドします。  
  
 `CAnimateCtrl`の使用の詳細については、[コントロール](../../mfc/controls-mfc.md) と [を使用して CAnimateCtrl](../Topic/Using%20CAnimateCtrl.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CAnimateCtrl`  
  
## 必要条件  
 **ヘッダー :** afxcmn.h  
  
## 参照  
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CAnimateCtrl::Create](../Topic/CAnimateCtrl::Create.md)   
 [ON\_CONTROL](../Topic/ON_CONTROL.md)