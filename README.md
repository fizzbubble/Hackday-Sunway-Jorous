# Hackday-Sunway-Jorous
public class ClasspageActivity extends ListActivity {

    ListView listView;
    ArrayAdapter<String> adapter;
    final Context Context = this;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.classpage);

String[] classrooms = {"ROOM 1.1", "ROOM 2.2", "LAB 1.1", "LAB 1.2", "HALL 1.1", "HALL 1.2"};
        ArrayAdapter<String> adapter = new ArrayAdapter<String>(getListView().getContext(), android.R.layout.simple_list_item_1, classrooms);
        getListView().setAdapter(adapter);

        listView = (ListView)findViewById(R.id.listView);
        adapter = new ArrayAdapter<String>(this,android.R.layout.simple_list_item_1, classrooms);
        listView.setAdapter(adapter);
        listView.setOnItemClickListener(new AdapterView.OnItemClickListener() {
            @Override
            public void onItemClick(AdapterView<?> parent, View view, int position, long id) {
                Intent intent = new Intent (Context, TimingPage.class);
                startActivity(intent);
            }
        });
