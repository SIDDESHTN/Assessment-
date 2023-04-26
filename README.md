# Assessment-
int maximal(int n, int roads[][]) {
    vector<int> list[n];
    int roadIndex = 0;
    for(int i = 0; i < sizeof(roads); i++){
        list[roads[i][0]].push_back(roadIndex);
        list[roads[i][1]].push_back(roadIndex);
        roadIndex++;
    }
    int res = 0;
    for(int i = 0; i < n ; i++) 
{
        for(int j = 0 ; j < n ; j++)  
{
            if(i == j) continue;
            set<int> set;
            set.insert(list[i].begin(), list[i].end());
            set.insert(list[j].begin(), list[j].end());
            res = max(set.size(), res);
        }
    }
    return res;
}
