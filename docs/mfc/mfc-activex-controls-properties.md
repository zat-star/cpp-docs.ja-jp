---
title: "MFC ActiveX コントロール: プロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
- properties [MFC]
ms.assetid: b678a53c-0d9e-476f-8aa0-23b80baaba46
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eea42401255f0aa99dd7a42b8e9b69e45dfe7b5b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-properties"></a>MFC ActiveX コントロール : プロパティ
ActiveX コントロールは、コントロール コンテナーと通信するためにイベントを発生させます。 コンテナーでは、コントロールと通信するメソッドとプロパティを戻り値を使用します。 メソッドとプロパティを使用すると、目的のようなそれぞれ、メンバー関数と C++ のクラスのメンバー変数にします。 プロパティは、任意のコンテナーに公開されている ActiveX コントロールのデータ メンバーです。 プロパティは、オートメーション クライアントや ActiveX コントロール コンテナーなど、ActiveX コントロールを含むアプリケーションでインターフェイスを提供します。  
  
 プロパティは、属性とも呼ばれます。  
  
 ActiveX コントロールのメソッドの詳細については、記事を参照してください。 [MFC ActiveX コントロール: メソッド](../mfc/mfc-activex-controls-methods.md)です。  
  
 ActiveX コントロールには、在庫とカスタム メソッドおよびプロパティの両方を実装できます。 クラス`COleControl`ストック プロパティの実装を提供します。 (ストック プロパティの完全な一覧は、記事を参照してください[MFC ActiveX コントロール: ストック プロパティの追加](../mfc/mfc-activex-controls-adding-stock-properties.md)。)。開発者は、によって定義されたカスタムのプロパティは、ActiveX コントロールに特別な機能を追加します。 詳細については、次を参照してください。 [MFC ActiveX コントロール: カスタム プロパティの追加](../mfc/mfc-activex-controls-adding-custom-properties.md)です。  
  
 メソッドと同様に、カスタムおよびストックの両方のプロパティがプロパティ、メソッド、およびの既存のメンバー関数を処理するディスパッチ マップで構成されるメカニズムによってサポートされている、`COleControl`クラスです。 さらに、これらのプロパティは、開発者がコントロールに余分な情報を渡すために使用するパラメーターを持つことができます。  
  
 次の記事では、さらに詳しく ActiveX コントロールのプロパティについて説明します。  
  
-   [MFC ActiveX コントロール: ストック プロパティの追加](../mfc/mfc-activex-controls-adding-stock-properties.md)  
  
-   [MFC ActiveX コントロール: カスタム プロパティの追加](../mfc/mfc-activex-controls-adding-custom-properties.md)  
  
-   [MFC ActiveX コントロール: 高度なプロパティの実装](../mfc/mfc-activex-controls-advanced-property-implementation.md)  
  
-   [MFC ActiveX コントロール: アンビエント プロパティへのアクセス](../mfc/mfc-activex-controls-accessing-ambient-properties.md)  
  
## <a name="see-also"></a>参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

