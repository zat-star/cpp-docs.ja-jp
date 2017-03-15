---
title: "アプリケーションの設定、MFC DLL ウィザード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.dll.appset
dev_langs:
- C++
helpviewer_keywords:
- MFC DLL Wizard, application settings
ms.assetid: 0a96b94f-ae36-4975-951b-c9ffb3def21c
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: df1e3de3e1548fe4c4c340a30127d9916998ba64
ms.lasthandoff: 02/24/2017

---
# <a name="application-settings-mfc-dll-wizard"></a>[アプリケーションの設定] (MFC DLL ウィザード)
デザインし、の基本的な機能を MFC DLL プロジェクトを新規に追加するには、MFC DLL ウィザードのこのページを使用します。  
  
## <a name="dll-type"></a>[DLL の種類]  
 作成する DLL の種類を選択します。  
  
 **共有の MFC DLL を使用するレギュラー DLL**  
 MFC ライブラリを共有 DLL としてプログラムにリンクするには、このオプションを選択します。 このオプションを使用すると、DLL と呼び出し元のアプリケーション間での MFC オブジェクトを共有できません。 プログラムでは、実行時に、MFC ライブラリへの呼び出しができます。 このオプションは、MFC ライブラリを使用する複数の実行ファイルで構成される場合に、プログラムのディスクとメモリの量を削減します。 Win32 と MFC の両方のプログラムは、DLL で関数を呼び出すことができます。 この種類のプロジェクトでは MFC DLL を再配布する必要があります。  
  
 **MFC での通常の DLL が静的にリンク**  
 MFC ライブラリをビルド時に、プログラムを静的にリンクするには、このオプションを選択します。 Win32 と MFC の両方のプログラムは、DLL で関数を呼び出すことができます。 このオプションでは、プログラムのサイズが増えますが、中には、この種類のプロジェクトでは MFC DLL を再配布する必要はありません。 MFC オブジェクトは、DLL と呼び出し元のアプリケーション間で共有できません。  
  
 **MFC 拡張 DLL**  
 場合は、プログラム実行時に、MFC ライブラリへの呼び出しを作成して、DLL と呼び出し元のアプリケーション間での MFC オブジェクトを共有する場合は、このオプションを選択します。 このオプションは、MFC ライブラリを使用する複数の実行可能ファイルで構成される場合に、プログラムのディスクとメモリの量を削減します。 MFC プログラムだけでは、DLL で関数を呼び出すことができます。 この種類のプロジェクトでは MFC DLL を再配布する必要があります。  
  
## <a name="additional-features"></a>その他の機能  
 Windows ソケットをサポートしているかどうかと、MFC DLL がオートメーションをサポートするかどうかを選択します。  
  
 **オートメーション**  
 選択**オートメーション**別のプログラムに実装されているオブジェクトを操作するプログラムを許可するようにします。 選択すると**オートメーション**も他のオートメーション クライアントにプログラムを公開します。 参照してください[オートメーション](../../mfc/automation.md)の詳細。  
  
 **Windows ソケット**  
 プログラムが Windows ソケットをサポートしていることを示すためには、このオプションを選択します。 Windows ソケットを使用すると、TCP/IP ネットワーク経由で通信するプログラムを作成できます。  
  
 Windows で、MFC DLL のソケットのサポートが作成された、[場合は](../../mfc/reference/cwinapp-class.md#initinstance)ソケットの初期化をサポートし、MFC ヘッダー ファイル StdAfx.h AfxSock.h が含まれています。  
  
## <a name="see-also"></a>関連項目  
 [MFC DLL ウィザード](../../mfc/reference/mfc-dll-wizard.md)   
 [MFC DLL プロジェクトの作成](../../mfc/reference/creating-an-mfc-dll-project.md)


