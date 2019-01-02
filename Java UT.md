mockito
https://www.cnblogs.com/Ming8006/p/6297333.html

mockito
when(configurationProvider.getObjectDefinition(isA(Class.class)).thenReturn(objDef);


mockit
mock method
new MockUp<GenericObjectToLazyBean>() {
      @mockit.Mock
      MentoringProgramMatchedParticipant transform(GenericObject eo) {
        final MentoringProgramMatchedParticipant part1 = new MentoringProgramMatchedParticipant();
        return part1;
      }
    };

mock new instance constructor
new MockUp<GenericObjectToLazyBean>() {
      @mockit.Mock
      public void $init() {}
    };

mock statis/private field when new the class
new MockUp<GenericObjectToLazyBean>() {
      @mockit.Mock
      public void $clinit() {}
    };


public void testGetValidMatchedParticipantsByUserId_for_mentor(@Mocked GOSQLGeneratorContext search)
new Verifications() {{
      List<Criterion> restirctions = new ArrayList<>();
      search.add(withCapture(restirctions));
      Assert.assertEquals(restirctions.size(), 2);
      com.successfactors.genericobject.api.sql.Criterion expected1 = Restrictions.in("mentorshipStatus", MentorshipStatusEnum.getValidStatusList());
      Assert.assertTrue(EqualsBuilder.reflectionEquals(restirctions.get(0), expected1));
      Assert.assertEquals(restirctions.get(1).getBindValues(Locale.US), Arrays.asList("cgrant1", "1234"));
      Assert.assertEquals(restirctions.get(1).getFieldsInvolved(), Arrays.asList("mentor", "programId"));
    }};


Deencapsulation class for execute classes

// same as below 2
// issue is Could not only capture the mentioned Class type argument but all, so require to set time to the number where the method been executed without the class type
ArgumentCaptor<DeleteGenericObjectsByIds> argument = ArgumentCaptor.forClass(DeleteGenericObjectsByIds.class);
verify(scaHandler, times(2)).execute(argument.capture());
System.out.println(argument.getAllValues());
      
verify(scaHandler, times(2)).execute(argThat(new ArgumentMatcher<DeleteGenericObjectsByIds>() {
@Override
public boolean matches(Object o) {
  if (o instanceof DeleteGenericObjectsByIds) {
    DeleteGenericObjectsByIds param = (DeleteGenericObjectsByIds)o;
    boolean isContainAllIdsWhenDelete = param.getIDs().containsAll(Arrays.asList(1234L, 2345L, 3456L));
    return isContainAllIdsWhenDelete;
  }
  return true;
}
}));


to verify the object is been touched or not (exclude already verified method)
for example after executed the production code, the program only be called to getExternalIdString once and no other code to touch. so after verify the getExternalIdString, using verifyNoMoreInteractions to ensure no other touch of program. (including getter and setter)
verify(program, times(1)).getExternalIdString();
verifyNoMoreInteractions(program);

verify(program, atLeast(0)).getExternalIdString();
