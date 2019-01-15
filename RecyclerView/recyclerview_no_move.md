###  RecyclerView 禁用滑动

自定义LayoutManager进行处理，这里以LinearLayoutManger为例，其他类似

```java
public class MyLayoutManager extends LinearLayoutManager {
    private boolean isScrollEnabled = true;

    public MyLayoutManager(Context context, AttributeSet attrs, int defStyleAttr, int defStyleRes) {
        super(context, attrs, defStyleAttr, defStyleRes);
    }

    public MyLayoutManager(Context context) {
        super(context);
    }

    public MyLayoutManager(Context context, int orientation, boolean reverseLayout) {
        super(context, orientation, reverseLayout);
    }

    /*调用这个方法控制滑动*/
    public void setScrollEnabled(boolean flag) {
        this.isScrollEnabled = flag;
    }

    @Override
    public boolean canScrollVertically() {
        return isScrollEnabled && super.canScrollVertically();
    }
}

```









