# partition
解耦、项目划分

<!-- 一对多的映射关系 -->
      <resultMap id="BaseResultMap" type="com.wgc.maven_blog.entity.Articles">
         <id column="id" jdbcType="INTEGER" property="id" />
         <result column="user_id" jdbcType="INTEGER" property="userId" />
         <result column="title" jdbcType="VARCHAR" property="title" />
         <result column="read_number" jdbcType="INTEGER" property="readNumber" />
         <result column="comment_count" jdbcType="INTEGER" property="commentCount" />
         <result column="publish_date" jdbcType="TIMESTAMP" property="publishDate" />
         <result column="upvote_number" jdbcType="INTEGER" property="upvoteNumber" />
         <result column="favor_number" jdbcType="INTEGER" property="favorNumber" />
         <result column="content" jdbcType="LONGVARCHAR" property="content" />
         <!-- 嵌入附属表 ， association是多对一个的关系 -->
         <association property="favors" javaType="com.wgc.maven_blog.entity.Favor"     resultMap="com.wgc.maven_blog.dao.FavorMapper.BaseResultMap" autoMapping="true"></association>
         <association property="comments" javaType="com.wgc.maven_blog.entity.Comments" resultMap="com.wgc.maven_blog.dao.CommentsMapper.BaseResultMap" autoMapping="true"></association>
         <association property="users" javaType="com.wgc.maven_blog.entity.Users" resultMap="com.wgc.maven_blog.dao.UsersMapper.BaseResultMap" autoMapping="true"></association>
         <association property="reads" javaType="com.wgc.maven_blog.entity.Read" resultMap="com.wgc.maven_blog.dao.ReadMapper.BaseResultMap" autoMapping="true"></association>
         <association property="shares" javaType="com.wgc.maven_blog.entity.Share" resultMap="com.wgc.maven_blog.dao.ShareMapper.BaseResultMap" autoMapping="true"></association>
         <association property="upvotes" javaType="com.wgc.maven_blog.entity.Upvote" resultMap="com.wgc.maven_blog.dao.UpvoteMapper.BaseResultMap" autoMapping="true" ></association>


       <!-- collection 是一对多的关系 -->
       <collection property="users" resultMap="com.wgc.maven_blog.dao.UsersMapper.BaseResultMap" autoMapping="true"></collection>
       
       
       </resultMap>
       
