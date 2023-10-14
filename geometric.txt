#GEOMETRIC POLYTOPES

LoadPackage("sonata");#Needed for IsIsomorphicGroup


Print("-------------------------------\n",
"GEOMETRIC POLYTOPES\n",
"-------------------------------\n\n");


# Define the golden ratio
rho := (1 + Sqrt(5)) / 2;

# Define the matrices
R0 := (1/2) * [ [rho, 1, 0, -1 + rho],
                [1, 1 - rho, 0, -rho],
                [0, 0, 2, 0],
                [-1 + rho, -rho, 0, 1] ];

R1 := [ [1, 0, 0, 0],
        [0, 1, 0, 0],
        [0, 0, 1, 0],
        [0, 0, 0, -1] ];

R2 := (1/2) * [ [2, 0, 0, 0],
                [0, rho, -1, rho - 1],
                [0, -1, 1 - rho, rho],
                [0, rho - 1, rho, 1] ];

R3 := [ [1, 0, 0, 0],
        [0, 1, 0, 0],
        [0, 0, -1, 0],
        [0, 0, 0, 1] ];

g:=Group([R0,R1,R2,R3]);#Group of the 600-cell

P0:=R0;
P1:=R1*R2*R3*R2*R1*R0*R1*R2*R3*R2*R1;
P2:=R3;
P3:=R2;

h:=Group([P0,P1,P2,P3]);#Group of the starry {5/2,3,5}

S1:=P0*P1*P3*P2;
S2:=P2*P1;
S3:=P3*P2;

q:=Subgroup(h,[S1,S2,S3]);#Group of the chiral {(12/1,5),3,5}
fq:=Subgroup(h,[S1,S2]);#Face group of the chiral {(12/1,5),3,5}


#Define a function to act on sets of sets of sets (cells)
OnSetsSetsSets:=
function(cell,g)
	return Set(List(cell, function ( i )
		return OnSetsSets(i,g);
		end ) );
	end;


Print("-------------------------------\n",
"STRING RELATIONS OF {5/2,3,5} \n");
Print("|<P0>|=", Order(P0), "\n");
Print("|<P1>|=", Order(P1), "\n");
Print("|<P2>|=", Order(P2), "\n");
Print("|<P3>|=", Order(P3), "\n\n");

Print("|<P0*P1>|=", Order(P0*P1), "\n");
Print("|<P1*P2>|=", Order(P1*P2), "\n");
Print("|<P2*P3>|=", Order(P2*P3), "\n\n");

Print("|<P0*P2>|=", Order(P0*P2), "\n");
Print("|<P0*P3>|=", Order(P0*P3), "\n");
Print("|<P1*P3>|=", Order(P1*P3), "\n\n");

Print("Are the groups of {3,3,5} and {5/2,3,5} the same? ", g=h,"\n\n\n");


Print("-------------------------------\n",
"BASE VERTEX OF {5/2,3,5}\n\n");

v0:=[1,0,0,0];
w0:=OnPoints(v0,R0*R1*R2*R1*R2*R3*R2*R1*R3*R2*R3*R2*R1*R2*R3*R2*R1);

Print("w0P0=w0 ",OnPoints(w0,P0)=w0,"\n");
Print("w0P1=w0 ",OnPoints(w0,P1)=w0,"\n");
Print("w0P2=w0 ",OnPoints(w0,P2)=w0,"\n");
Print("w0P3=w0 ",OnPoints(w0,P3)=w0,"\n\n\n");


Print("-------------------------------\n",
"FACE COUNT OF THE THREE POLYTOPES\n");


Print("\n","{3,3,5}","\n","\n");

FvRC:=Orbit(Subgroup(g,[R0,R1]),v0,OnPoints);#Vertices in the face
CvRC:=Orbit(Subgroup(g,[R0,R1,R2]),v0,OnPoints);#Vertices in the cell
PvRC:=Orbit(g,v0,OnPoints);#Vertices in the polytope
eRC:=[v0,OnRight(v0,R0)];#Basic edge
EfRC:=Orbit(Subgroup(g,[R0,R1]),SortedList(eRC),OnSets);#Edges in the face
EcRC:=Orbit(Subgroup(g,[R0,R1,R2]),SortedList(eRC),OnSets);#Edges in the cell
EpRC:=Orbit(g,SortedList(eRC),OnSets);#Edges in the polytope
FcRC:=Orbit(Subgroup(g,[R0,R1,R2]),SortedList(EfRC),OnSetsSets);#Faces in the cell
FpRC:=Orbit(g,SortedList(EfRC),OnSetsSets);#Faces in the polytope
CpRC:=Orbit(g,SortedList(FcRC),OnSetsSetsSets);#Cells in the polytope

Print("Vertices in the face: ",Size(FvRC),"\n");
Print("Vertices in the cell: ",Size(CvRC),"\n");
Print("Vertices in the polytope: ",Size(PvRC),"\n");
Print("Edges in the face: ",Size(EfRC),"\n");
Print("Edges in the cell: ",Size(EcRC),"\n");
Print("Edges in the polytope: ",Size(EpRC),"\n");
Print("Faces in the cell: ",Size(FcRC),"\n");
Print("Faces in the polytope: ",Size(FpRC),"\n");
Print("Cells in the polytope: ",Size(CpRC),"\n","\n","\n");


Print("{5/2,3,5}","\n","\n");

FvRS:=Orbit(Subgroup(h,[P0,P1]),w0,OnPoints);#Vertices in the face
CvRS:=Orbit(Subgroup(h,[P0,P1,P2]),w0,OnPoints);#Vertices in the cell
PvRS:=Orbit(h,w0,OnPoints);#Vertices in the polytope
eRS:=[w0,OnRight(w0,P0)];#Basic edge
EfRS:=Orbit(Subgroup(h,[P0,P1]),SortedList(eRS),OnSets);#Edges in the face
EcRS:=Orbit(Subgroup(h,[P0,P1,P2]),SortedList(eRS),OnSets);#Edges in the cell
EpRS:=Orbit(h,SortedList(eRS),OnSets);#Edges in the polytope
FcRS:=Orbit(Subgroup(h,[P0,P1,P2]),SortedList(EfRS),OnSetsSets);#Faces in the cell
FpRS:=Orbit(h,SortedList(EfRS),OnSetsSets);#Faces in the polytope
CpRS:=Orbit(h,SortedList(FcRS),OnSetsSetsSets);#Cells in the polytope

Print("Vertices in the face: ",Size(FvRS),"\n");
Print("Vertices in the cell: ",Size(CvRS),"\n");
Print("Vertices in the polytope: ",Size(PvRS),"\n");
Print("Edges in the face: ",Size(EfRS),"\n");
Print("Edges in the cell: ",Size(EcRS),"\n");
Print("Edges in the polytope: ",Size(EpRS),"\n");
Print("Faces in the cell: ",Size(FcRS),"\n");
Print("Faces in the polytope: ",Size(FpRS),"\n");
Print("Cells in the polytope: ",Size(CpRS),"\n","\n","\n");


Print("Chiral","\n","\n");

FvC:=Orbit(Subgroup(q,[S1]),w0,OnPoints);#Vertices in the face
CvC:=Orbit(Subgroup(q,[S1,S2]),w0,OnPoints);#Vertices in the cell
PvC:=Orbit(q,w0,OnPoints);#Vertices in the polytope
eC:=[w0,OnRight(w0,S1^-1)];#Basic edge
EfC:=Orbit(Subgroup(q,[S1]),SortedList(eC),OnSets);#Edges in the face
EcC:=Orbit(Subgroup(q,[S1,S2]),SortedList(eC),OnSets);#Edges in the cell
EpC:=Orbit(q,SortedList(eC),OnSets);#Edges in the polytope
FcC:=Orbit(Subgroup(q,[S1,S2]),SortedList(EfC),OnSetsSets);#Faces in the cell
FpC:=Orbit(q,SortedList(EfC),OnSetsSets);#Faces in the polytope
CpC:=Orbit(q,SortedList(FcC),OnSetsSetsSets);#Cells in the polytope

Print("Vertices in the face: ",Size(FvC),"\n");
Print("Vertices in the cell: ",Size(CvC),"\n");
Print("Vertices in the polytope: ",Size(PvRC),"\n");
Print("Edges in the face: ",Size(EfC),"\n");
Print("Edges in the cell: ",Size(EcC),"\n");
Print("Edges in the polytope: ",Size(EpC),"\n");
Print("Faces in the cell: ",Size(FcC),"\n");
Print("Faces in the polytope: ",Size(FpC),"\n");
Print("Cells in the polytope: ",Size(CpC),"\n\n\n");

#Maybe double check that SetsSetsSets is correctly defined


Print("-------------------------------\n",
"STRING RELATIONS OF CHIRAL\n\n");
Print("|<S1>|=", Order(S1), "\n");
Print("|<S2>|=", Order(S2), "\n");
Print("|<S3>|=", Order(S3), "\n\n");

Print("|<S1*S2>|=", Order(S1*S2), "\n");
Print("|<S1*S2*S3>|=", Order(S1*S2*S3), "\n");
Print("|<S2*S3>|=", Order(S2*S3), "\n\n\n");

#Print("|<S1,S2>|=", Size(Subgroup(g,[S1,S2])),"\n"); FACE
#Print("|<S1,S2,S3>|=", Size(Subgroup(g,[S1,S2,S3])),"\n"); CELL



Print("-------------------------------\n",
"STABILIZERS OF CHIRAL\n\n");

Print("S3 fixes the base vertex and edge?","\n\n");

Print("w0.S3=w0  ",w0=OnPoints(w0,S3),"\n");
Print("w0.S1^-1.S3=w0.S1^-1  ", OnRight(w0,S1^-1)=OnRight(OnRight(w0,S1^-1),S3),"\n\n\n");


Print("Stabilizers within the cell","\n\n");

Print("Stab_<S1,S2>w0=<S2>  ", IsIsomorphicGroup(Stabilizer(fq,w0),Subgroup(q,[S2])),"\n");
Print("Stab_<S1,S2>e=<S1*S2>  ", IsIsomorphicGroup(Stabilizer(fq,SortedList(eC),OnSets),Subgroup(q,[S1*S2])),"\n");
Print("Stab_<S1,S2>f=<S1>  ", IsIsomorphicGroup(Stabilizer(fq,SortedList(EfC),OnSetsSets),Subgroup(q,[S1])),"\n\n\n");

Print("Stabilizers within the whole polytope","\n\n");

Print("Stab_<S1,S2,S3>w0=<S2,S3>  ", IsIsomorphicGroup(Stabilizer(q,w0),Subgroup(q,[S2,S3])),"\n");
Print("Stab_<S1,S2,S3>e=<S1*S2,S3>  ", IsIsomorphicGroup(Stabilizer(q,SortedList(eC),OnSets),Subgroup(q,[S1*S2,S3])),"\n");
Print("Stab_<S1,S2,S3>f=<S1,S2*S3>  ", IsIsomorphicGroup(Stabilizer(q,SortedList(EfC),OnSetsSets),Subgroup(q,[S1,S2*S3])),"\n");
Print("Stab_<S1,S2,S3>c=<S1,S2>  ", IsIsomorphicGroup(Stabilizer(q,SortedList(FcC),OnSetsSetsSets),Subgroup(q,[S1,S2])));


#CENTROID OF THE BASE CELL

rt:=RightTransversal(Subgroup(h,[P0,P1,P2]),Subgroup(h,[P1,P2]));
sum:=[0,0,0,0];

for i in [1..Size(rt)] do
	sum:=sum+OnPoints(w0,rt[i]);
od;

average:=sum/20;
