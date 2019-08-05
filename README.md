# Binding SelectedItem in Listview

ListView support to select the items through binding the [SelectedItem](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~SelectedItem.html) property from view model by implementing the `INotifyPropertyChanged` interface that gives the call back notification to UI.

```
<syncfusion:SfListView x:Name="listView" 
                       SelectedItem="{Binding SelectedItem}"
                       ItemsSource="{Binding BookInfoCollection}"/>
```
```
//ViewModel.cs
public class BookInfoRepository : INotifyPropertyChanged
{
    private object selectedItem;
    public object SelectedItem
    {
        get { return this.selectedItem; }
        set
        {
            this.selectedItem = value;
            this.OnPropertyChanged("SelectedItem");
        }
    }
    public BookInfoRepository()
    {
        SelectedItem = BookInfoCollection[2];
    }
}
```
To know more about MVVM in ListView, please refer our documentation [here](https://help.syncfusion.com/xamarin/sflistview/mvvm)