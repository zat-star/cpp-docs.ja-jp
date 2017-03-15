---
title: "オプション、ATL コントロール ウィザード | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.control.options"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL コントロール ウィザード、オプション"
ms.assetid: 4607c51a-992d-433e-9281-919c6f519a3d
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# オプション、ATL コントロール ウィザード
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ここに "検索結果" の概要を挿入します。  
  
 ウィザードのこのページを使用して、作成するコントロールの種類とコントロールに含めるインターフェイス サポートのレベルを定義します。  
  
## UIElement の一覧  
 **\[コントロール型\]**  
 作成するコントロールの種類。  
  
-   **\[標準コントロール\]: ActiveX コントロール**  
  
-   **\[複合コントロール\]**: ダイアログ ボックスと同様に、他の ActiveX コントロールや Windows コントロールを含めることができる ActiveX コントロールです。  複合コントロールの種類は以下のとおりです。  
  
    -   複合コントロールを実装するダイアログ ボックスのテンプレート  
  
    -   起動時に複合コントロールを自動的に登録するカスタム リソース REGISTRY  
  
    -   複合コントロールを実装する C\+\+ クラス  
  
    -   複合コントロールによって公開される COM インターフェイス  
  
    -   複合コントロールを含む HTML テスト ページ  
  
     既定では、このコントロールは [CComControlBase::m\_bWindowOnly](../Topic/CComControlBase::m_bWindowOnly.md) を true に設定します。この値は、ウィンドウを持つコントロールであることを示します。  このコントロールはシンク マップを実装します。  詳細については、「[DHTML コントロールのサポート](../../atl/atl-support-for-dhtml-controls.md)」を参照してください。  
  
-   **\[DHTML コントロール\]**: ATL DHTML コントロールは、HTML を使用して、ユーザー インターフェイスを指定します。  DHTML UI クラスには COM マップが含まれます。  既定では、このコントロールは [CComControlBase::m\_bWindowOnly](../Topic/CComControlBase::m_bWindowOnly.md) を true に設定します。この値は、ウィンドウを持つコントロールであることを示します。  
  
     詳細については、「[DHTML コントロール プロジェクトの要素の識別](../../atl/identifying-the-elements-of-the-dhtml-control-project.md)」を参照してください。  
  
 **\[ライト コントロール\]**  
 ほとんどのコンテナーに必須のインターフェイスだけがサポートされます。  **\[ライト コントロール\]** はすべての種類のコントロールに対して設定できます。ミニマル標準コントロール、ミニマル複合コントロール、およびミニマル DHTML コントロールを作成できます。  
  
 **\[集約\]**  
 作成するコントロールに集約サポートを追加します。  詳細については、「[集約](../../atl/aggregation.md)」を参照してください。  
  
-   **\[はい\]**: 集約できるコントロールが作成されます。  
  
-   **\[いいえ\]**: 集約できないコントロールが作成されます。  
  
-   **\[アグリゲーションのみ\]**: 集約を通じてのみインスタンス化されるコントロールが作成されます。  
  
 **\[スレッド モデル\]**  
 コントロールで使用するスレッド化モデルを指定します。  
  
-   **\[シングル\]**: コントロールは、プライマリ COM スレッドだけで実行されます。  
  
-   **\[アパートメント\]**: コントロールは、任意のシングル スレッド アパートメントで作成できます。  既定値です。  
  
 **\[インターフェイス\]**  
 このコントロールがコンテナーに対して公開するインターフェイスの種類。  
  
-   **\[デュアル\]**: `IDispatch` を使用して、または VTBL によって直接、プロパティとメソッドを公開するインターフェイスが作成されます。  
  
-   **\[カスタム\]**: VTBL によって直接メソッドを公開するインターフェイスが作成されます。  
  
     **\[カスタム\]** を選択すると、コントロールが **\[オートメーション互換\]** であることを指定できます。  **\[オートメーション互換\]** を選択すると、ウィザードによって [oleautomation](../../windows/oleautomation.md) 属性が IDL 内のインターフェイスに追加されます。このインターフェイスは oleaut32.dll 内の汎用マーシャラーでマーシャリングできます。  詳細については、[!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] の「[Marshaling Details](http://msdn.microsoft.com/library/windows/desktop/ms692621)」を参照してください。  
  
     また、**\[オートメーション互換\]** を選択する場合は、コントロール内のすべてのメソッドのすべてのパラメーターを **VARIANT** 互換にする必要があります。  
  
 **\[サポート\]**  
 コントロールのその他のサポートを設定します。  
  
-   **\[接続ポイント\]**: オブジェクトのクラスを [IConnectionPointContainerImpl](../Topic/IConnectionPointContainerImpl%20Class.md) から派生させ、その派生クラスでソース インターフェイスを公開できるようにすることによって、オブジェクトのコネクション ポイントを有効にします。  
  
-   **\[ライセンス\]**: [ライセンス処理](http://msdn.microsoft.com/library/windows/desktop/ms690543)用のサポートをコントロールに追加します。  ライセンス コントロールをホストできるのは、クライアント コンピューターに適切なライセンスがある場合だけです。  
  
## 参照  
 [ATL コントロール ウィザード](../../atl/reference/atl-control-wizard.md)