---
title: "インターフェイス (Visual C) を実装する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: interfaces, implementing
ms.assetid: 72f8731b-7e36-45db-8b10-7ef211a773cd
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 896ada2c46c68a794265e7344e9b7f7c7f91aebe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-an-interface-visual-c"></a>インターフェイスの実装 (Visual C++)
インターフェイスを実装するには、ATL COM アプリケーションまたは ATL サポートを含む MFC アプリケーションとしてにプロジェクトを作成が必要があります。 使用することができます、 [ATL プロジェクト ウィザード](../atl/reference/atl-project-wizard.md)ATL アプリケーションを作成するか、 [ATL オブジェクトを MFC アプリケーションに追加](../mfc/reference/adding-atl-support-to-your-mfc-project.md)MFC アプリケーションに対する ATL のサポートを実装します。  
  
 インターフェイスを実装する、プロジェクトを作成した後は、まず ATL オブジェクトを追加する必要があります。 参照してください[を追加するオブジェクトと ATL プロジェクトへのコントロールの](../atl/reference/adding-objects-and-controls-to-an-atl-project.md)ATL プロジェクトにオブジェクトを追加するウィザードの一覧についてはします。  
  
> [!NOTE]
>  ウィザードでは、ATL ダイアログ、ATL、パフォーマンス オブジェクト、およびパフォーマンス カウンターを使用する XML Web サービスはサポートされていません。  
  
 場合する[ATL コントロールを追加](../atl/reference/adding-an-atl-control.md)に記載されている既定のインターフェイスを実装するかどうかを指定することができます、[インターフェイス](../atl/reference/interfaces-atl-control-wizard.md)そのウィザードと atlcom.h で定義されているのページです。  
  
 オブジェクトまたはコントロールを追加した後インターフェイス実装ウィザードを使用して、任意の利用可能なタイプ ライブラリ内にある他のインターフェイスを実装できます。  
  
 新しいインターフェイスを追加する場合 プロジェクトの .idl ファイルをそれを手動で追加する必要があります。 参照してください[ATL プロジェクトで、新しいインターフェイスを追加](../atl/reference/adding-a-new-interface-in-an-atl-project.md)詳細についてはします。  
  
### <a name="to-implement-an-interface"></a>インターフェイスを実装するには  
  
1.  クラス ビューでは、ATL オブジェクトのクラス名を右クリックします。  
  
2.  をクリックして**追加**クリックしてショートカット メニューから**インターフェイスの実装**を表示する、[インターフェイス実装ウィザード](../ide/implement-interface-wizard.md)です。  
  
3.  該当するタイプ ライブラリから実装し、をクリックするインターフェイスを選択**完了**です。  
  
4.  クラス ビューで、展開オブジェクトのベースとインターフェイスを実装し、使用可能なプロパティ、メソッド、およびイベントを表示するインターフェイスのノードを展開するインターフェイスを参照してください。  
  
    > [!NOTE]
    >  使用することも、[オブジェクト ブラウザー](http://msdn.microsoft.com/en-us/f89acfc5-1152-413d-9f56-3dc16e3f0470)インターフェイスのメンバーを参照します。  
  
## <a name="see-also"></a>参照  
 [COM インターフェイスの作成](../ide/creating-a-com-interface-visual-cpp.md)   
 [COM インターフェイスの編集](../ide/editing-a-com-interface.md)