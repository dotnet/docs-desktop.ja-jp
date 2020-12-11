---
title: マウス入力のしくみ
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- Windows Forms, mouse input
- mouse [Windows Forms], input
ms.assetid: 48fc5240-75a6-44bf-9fce-6aa21b49705a
ms.openlocfilehash: 39977be71054a16baf9be81c566eb3cdca09a916
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974368"
---
# <a name="how-mouse-input-works-in-windows-forms"></a>Windows フォームにおけるマウス入力のしくみ
マウス入力の受信と処理は、すべての Windows アプリケーションの重要な部分です。 マウスイベントを処理してアプリケーションでアクションを実行したり、マウスの位置情報を使用してヒットテストやその他のアクションを実行したりすることができます。 また、アプリケーション内のコントロールがマウス入力を処理する方法を変更することもできます。 このトピックでは、これらのマウスイベントの詳細と、マウスのシステム設定を取得および変更する方法について説明します。 マウスイベントによって提供されるデータと、マウスクリックイベントが発生する順序の詳細については、「 [Windows フォームのマウスイベント](mouse-events-in-windows-forms.md)」を参照してください。  
  
## <a name="mouse-location-and-hit-testing"></a>マウスの位置と Hit-Testing  
 ユーザーがマウスを動かすと、オペレーティングシステムはマウスポインターを移動します。 マウスポインターには、ホットスポットと呼ばれる1つのピクセルが含まれています。これは、オペレーティングシステムがポインターの位置として追跡し、認識します。 ユーザーがマウスを動かすか、マウスボタンを押すと、を <xref:System.Windows.Forms.Control> 含むが <xref:System.Windows.Forms.Cursor.HotSpot%2A> 適切なマウスイベントを発生させます。 <xref:System.Windows.Forms.MouseEventArgs.Location%2A> <xref:System.Windows.Forms.MouseEventArgs> マウスイベントを処理するとき、またはクラスのプロパティを使用して、のプロパティを使用して現在のマウス位置を取得でき <xref:System.Windows.Forms.Cursor.Position%2A> <xref:System.Windows.Forms.Cursor> ます。 その後、マウスの位置情報を使用してヒットテストを実行し、マウスの位置に基づいてアクションを実行できます。 ヒットテスト機能は <xref:System.Windows.Forms.ListView> 、、、およびコントロールなどの Windows フォームのいくつかのコントロールに組み込まれてい <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.MonthCalendar> <xref:System.Windows.Forms.DataGridView> ます。 適切なマウスイベントと共に使用され <xref:System.Windows.Forms.Control.MouseHover> ます。たとえば、ヒットテストは、アプリケーションで特定のアクションを実行する必要があるかどうかを判断する場合に非常に便利です。  
  
## <a name="mouse-events"></a>マウス イベント  
 マウス入力に応答する主な方法は、マウスイベントを処理することです。 次の表は、マウスイベントと、そのイベントが発生したときの説明を示しています。  
  
|マウス イベント|説明|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.Click>|このイベントは、マウスボタンが離されたとき (通常はイベントの前) に発生し <xref:System.Windows.Forms.Control.MouseUp> ます。 このイベントのハンドラーは、型 <xref:System.EventArgs> の引数を受け取ります。 このイベントは、クリックがいつ発生するかを判断する必要がある場合にのみ処理します。|  
|<xref:System.Windows.Forms.Control.MouseClick>|このイベントは、ユーザーがマウスでコントロールをクリックしたときに発生します。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.MouseEventArgs> の引数を受け取ります。 クリックが発生したときにマウスに関する情報を取得する必要がある場合に、このイベントを処理します。|  
|<xref:System.Windows.Forms.Control.DoubleClick>|このイベントは、コントロールがダブルクリックされたときに発生します。 このイベントのハンドラーは、型 <xref:System.EventArgs> の引数を受け取ります。 このイベントは、ダブルクリックがいつ発生するかを判断する必要がある場合にのみ処理します。|  
|<xref:System.Windows.Forms.Control.MouseDoubleClick>|このイベントは、ユーザーがマウスでコントロールをダブルクリックしたときに発生します。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.MouseEventArgs> の引数を受け取ります。 ダブルクリックが発生したときにマウスに関する情報を取得する必要がある場合に、このイベントを処理します。|  
|<xref:System.Windows.Forms.Control.MouseDown>|このイベントは、マウスポインターがコントロール上にあり、ユーザーがマウスボタンを押すと発生します。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.MouseEventArgs> の引数を受け取ります。|  
|<xref:System.Windows.Forms.Control.MouseEnter>|このイベントは、コントロールの種類に応じて、マウスポインターがコントロールの境界線またはクライアント領域に入ったときに発生します。 このイベントのハンドラーは、型 <xref:System.EventArgs> の引数を受け取ります。|  
|<xref:System.Windows.Forms.Control.MouseHover>|このイベントは、マウスポインターがコントロールの上に置かれたときに発生します。 このイベントのハンドラーは、型 <xref:System.EventArgs> の引数を受け取ります。|  
|<xref:System.Windows.Forms.Control.MouseLeave>|このイベントは、コントロールの種類に応じて、マウスポインターがコントロールの境界線またはクライアント領域から離れると発生します。 このイベントのハンドラーは、型 <xref:System.EventArgs> の引数を受け取ります。|  
|<xref:System.Windows.Forms.Control.MouseMove>|このイベントは、マウスポインターがコントロール上に移動したときに発生します。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.MouseEventArgs> の引数を受け取ります。|  
|<xref:System.Windows.Forms.Control.MouseUp>|このイベントは、マウスポインターがコントロール上にあり、ユーザーがマウスボタンを離すと発生します。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.MouseEventArgs> の引数を受け取ります。|  
|<xref:System.Windows.Forms.Control.MouseWheel>|このイベントは、コントロールにフォーカスがあるときにユーザーがマウスホイールを回転させたときに発生します。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.MouseEventArgs> の引数を受け取ります。 のプロパティを使用して、 <xref:System.Windows.Forms.MouseEventArgs.Delta%2A> <xref:System.Windows.Forms.MouseEventArgs> マウスのスクロール距離を決定できます。|  
  
## <a name="changing-mouse-input-and-detecting-system-settings"></a>マウス入力の変更とシステム設定の検出  
 コントロールからを派生させ、メソッドとメソッドを使用して、コントロールがマウス入力を処理する方法を検出および変更でき <xref:System.Windows.Forms.Control.GetStyle%2A> <xref:System.Windows.Forms.Control.SetStyle%2A> ます。 メソッドは、 <xref:System.Windows.Forms.Control.SetStyle%2A> 値のビットごとの組み合わせを取得して、 <xref:System.Windows.Forms.ControlStyles> コントロールが標準のクリックまたはダブルクリックの動作を持つかどうか、またはコントロールが独自のマウス処理を処理するかどうかを判断します。 また、クラスには、 <xref:System.Windows.Forms.SystemInformation> マウスの機能を説明するプロパティや、オペレーティングシステムとの対話方法を指定するプロパティが含まれています。 次の表は、これらのプロパティをまとめたものです。  
  
|プロパティ|説明|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>|2回のクリックがダブルクリックであることをオペレーティングシステムが考慮するために、ユーザーが2回クリックする必要がある領域のサイズ (ピクセル単位) を取得します。|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A>|オペレーティングシステムがマウス操作をダブルクリックすることを考慮するために、最初のクリックから2回目のクリックまでに経過する最大時間 (ミリ秒単位) を取得します。|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtons%2A>|マウスのボタンの数を取得します。|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtonsSwapped%2A>|左右のマウス ボタンの機能が入れ替わっているかどうかを示す値を取得します。|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverSize%2A>|マウス静止メッセージが生成されるためにマウス静止時間が経過するまでマウス ポインターをとどめておく必要がある四角形の領域のサイズ (ピクセル単位) を取得します。|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverTime%2A>|マウス静止メッセージが生成されるために静止領域内にマウス ポインターをとどめておく必要がある時間 (ミリ秒単位) を取得します。|  
|<xref:System.Windows.Forms.SystemInformation.MousePresent%2A>|マウスが取り付けられているかどうかを示す値を取得します。|  
|<xref:System.Windows.Forms.SystemInformation.MouseSpeed%2A>|現在のマウスの速度 (1 ~ 20) を示す値を取得します。|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelPresent%2A>|マウス ホイール付きのマウスが取り付けられているかどうかを示す値を取得します。|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollDelta%2A>|1つのマウスホイールの回転の増分値の量を取得します。|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollLines%2A>|マウス ホイールを回転したときにスクロールする行数を取得します。|  
  
## <a name="see-also"></a>関連項目

- [Windows フォーム アプリケーションにおけるマウス入力](mouse-input-in-a-windows-forms-application.md)
- [Windows フォームにおけるマウスのキャプチャ](mouse-capture-in-windows-forms.md)
- [Windows フォームにおけるマウス ポインター](mouse-pointers-in-windows-forms.md)
