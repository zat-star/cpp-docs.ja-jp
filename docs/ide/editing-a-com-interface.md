---
title: "COM インターフェイスの編集 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.com.editing.interfaces
dev_langs: C++
helpviewer_keywords:
- methods [C++], adding to COM interfaces
- COM interfaces, editing
- properties [C++], adding to COM interfaces
ms.assetid: 6c2909e0-af2d-4a37-bb39-ed372e6129cf
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b8911f23ce8e28f2da13c3d8305f4f13a861bb60
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="editing-a-com-interface"></a>COM インターフェイスの編集
クラス ビューのショートカット メニューからコマンドを使用すると、Visual C プロジェクトで新しいメソッドと、COM インターフェイスのプロパティを定義できます。 さらに、ツールボックスから、ActiveX コントロールのイベントを定義できます。  
  
 クラスに対しては ATL と MFC ベースで COM オブジェクト、クラスの実装時に、同じインターフェイスを編集することを行うことができます。  
  
> [!NOTE]
>  インターフェイスの外部で定義されている、**クラスの追加**ダイアログ ボックスで、Visual C、.idl ファイルにそのメソッドまたはプロパティを追加し、スタブをインターフェイスが手動で追加された場合でも、メソッドを実装するクラスが追加されます。  
  
 次の 3 つのウィザードを使用して、既存のインターフェイスをカスタマイズできます。 クラス ビューから利用可能なは。  
  
|ウィザード|プロジェクトの種類|  
|------------|------------------|  
|[プロパティの追加ウィザード](../ide/names-add-property-wizard.md)|ATL. をサポートする ATL または MFC のプロジェクト プロパティを追加するインターフェイスを右クリックします。<br /><br /> Visual C では、プロジェクトの種類が検出され、プロパティの追加ウィザードのオプションの変更を加えます。<br /><br /> -ディスパッチ インターフェイスを使用して作成されたプロジェクトの場合、 [MFC アプリケーション ウィザード](../mfc/reference/mfc-application-wizard.md)MFC に固有のオプションを提供するプロパティの追加ウィザードを起動します。<br />-の MFC ActiveX コントロールのインターフェイスは、プロパティの追加ウィザードは、ストック メソッドとそのまま使用したり、コントロールに合わせてカスタマイズできるプロパティの一覧を提供します。<br />-その他のすべてのインターフェイスに対しては、プロパティの追加ウィザードは、ほとんどの状況で便利なオプションを提供します。|  
|[メソッド追加ウィザード](../ide/add-method-wizard.md)|ATL. をサポートする ATL または MFC のプロジェクト メソッドを追加するインターフェイスを右クリックします。<br /><br /> Visual C では、プロジェクトの種類が検出され、メソッドの追加ウィザードのオプションの変更を加えます。<br /><br /> -ディスパッチ インターフェイスを使用して作成されたプロジェクトの場合、 [MFC アプリケーション ウィザード](../mfc/reference/mfc-application-wizard.md)MFC に固有のオプションを提供するメソッドの追加ウィザードを起動します。<br />-の MFC ActiveX コントロールのインターフェイスは、メソッドの追加ウィザードは、ストック メソッドとそのまま使用したり、コントロールに合わせてカスタマイズできるプロパティの一覧を提供します。<br />-その他のすべてのインターフェイスに対して、**メソッドの追加**ウィザードは、ほとんどの状況で便利なオプションを提供します。|  
  
 クラス ビュー で、オブジェクトのコントロール クラスを右クリックし、COM コントロールに新しいインターフェイスを実装するさらに、[インターフェイスの実装](../ide/implement-interface-wizard.md)です。  
  
## <a name="see-also"></a>参照  
 [リソース ファイルの操作](../windows/working-with-resource-files.md)   
 [コード ウィザードによる機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Visual C++ プロジェクトの種類](../ide/visual-cpp-project-types.md)