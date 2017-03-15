---
title: "コネクション ポイントの実装 (Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コネクション ポイント [C++], 実装"
  - "コネクション ポイントの実装ウィザード [C++]"
ms.assetid: 5b37e4f9-73c9-4bef-b26d-365bc0662260
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# コネクション ポイントの実装 (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

接続ポイントの実装ウィザードを使用してコネクション ポイントを実装するには、プロジェクトを ATL COM アプリケーションまたは ATL サポートを含む MFC アプリケーションとして作成しておく必要があります。  [ATL プロジェクト ウィザード](../Topic/ATL%20Project%20Wizard.md)を使用して ATL アプリケーションを作成するか、または [MFC アプリケーションに ATL オブジェクトを追加](../mfc/reference/adding-atl-support-to-your-mfc-project.md)して MFC アプリケーション用の ATL サポートを実装できます。  
  
> [!NOTE]
>  MFC プロジェクトのコネクション ポイントの実装方法については、「[コネクション ポイント](../mfc/connection-points.md)」を参照してください。  
  
 プロジェクトを作成したら、コネクション ポイントを実装するために、まず ATL オブジェクトを追加します。  オブジェクトを ATL プロジェクトに追加するウィザードの一覧については、「[ATL プロジェクトへのオブジェクトとコントロールの追加](../atl/reference/adding-objects-and-controls-to-an-atl-project.md)」を参照してください。  
  
> [!NOTE]
>  このウィザードでは、ATL ダイアログ、ATL Server で作成された XML Web サービス、パフォーマンス オブジェクト、およびパフォーマンス カウンターはサポートされていません。  
  
 接続可能なオブジェクト \(ソース\) は、アウトゴーイング インターフェイスごとにコネクション ポイントを公開できます。  各アウトゴーイング インターフェイスは、オブジェクト上のクライアント \(シンク\) で実装できます。  詳細については、「[ATL コネクション ポイント](../atl/atl-connection-points.md)」を参照してください。  
  
### コネクション ポイントを実装するには  
  
1.  クラス ビューで、ATL オブジェクトのクラス名を右クリックします。  
  
2.  ショートカット メニューの \[追加\] をクリックし、\[接続ポイントの追加\] をクリックして[接続ポイントの実装ウィザード](../ide/implement-connection-point-wizard.md)を表示します。  
  
3.  実装するコネクション ポイント インターフェイスを該当するタイプ ライブラリから選択し、\[完了\] をクリックします。  
  
4.  クラス ビューで、各コネクション ポイント用に作成されたプロキシ クラスをチェックします。  クラスは CProxy*InterfaceName*\<T\> と表示され、[IConnectionPointImpl](../Topic/IConnectionPointImpl%20Class.md) から派生します。  
  
5.  コネクション ポイント クラスをダブルクリックして、コネクション ポイント クラスの定義を表示します。  
  
    -   独自のプロジェクトのインターフェイス用のコネクション ポイントを実装する場合は、次の定義が表示されます。  
  
        ```  
        template< class T >  
        class CProxyInterfaceName :  
           public IConnectionPointImpl< T, &IID_InterfaceName >  
        {  
        public:  
        };  
        ```  
  
         ローカル インターフェイスを実装する場合は、メソッドとプロパティがクラス本体に表示されます。  
  
    -   ほかのインターフェイス用のコネクション ポイントを実装する場合は、先頭に `Fire_` が付いたインターフェイスのメソッドが定義に含まれます。  
  
## 参照  
 [コード ウィザードを使用した機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [オブジェクトへのコネクション ポイントの追加](../atl/adding-connection-points-to-an-object.md)