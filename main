#include  <bits/stdc++.h>
using namespace std;

string NORM (string s){//обрабатываем знаки препинания в конце слова
	int pos = 0;
	char lit;
	while(pos<s.length()){
		lit = s[pos];
		if(lit==','||lit=='.'||lit=='!'||lit=='?'||lit==';'){
			break;
		}
		pos++;
	}
	if(pos!=0){
		s = s.substr(0, pos);
	}
	return s;
}


int main()
{
	char s[500];
	string str;
	int b;
	FILE *in, *out;
	unordered_map <string, int> Mymap;
	in = fopen("a.txt", "r");
	while(fscanf(in, "%s", s)!=EOF){
		str=s;
		
		str = NORM(str);
		
		auto got = Mymap.find (str);
		if(got!=Mymap.end()){
			b=got->second;
			Mymap.erase(str);
			Mymap.insert({str,b+1});
		}
		else{
			Mymap.insert({str,1});
		}
	}
	if ( (out = fopen("b.txt", "w")) == NULL) {
		exit(1);
	}

    for(auto it = Mymap.begin(); it != Mymap.end(); ++it){
		cout<<(*it).first<<" "<<(*it).second<<endl;
		str=(*it).first;
		b=it->second;
		strcpy(s, str.c_str());
		fprintf(out, "%s %d\n", s, b);
	}
	return 0;
}
