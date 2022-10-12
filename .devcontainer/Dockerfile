FROM ros:galactic-ros-base

ENV ROS_WS /ros2
ENV PKG_NAME roboclaw_interfaces
SHELL [ "bash", "-c"]

COPY .devcontainer/entrypoint.sh /
ENTRYPOINT [ "/entrypoint.sh" ]
CMD [ "bash" ]

RUN echo "source /entrypoint.sh" >> /root/.bashrc && \
	echo "source /root/.bashrc" >> /root/.bash_profile

RUN mkdir -p ${ROS_WS}/src

RUN ln -s /workspaces/${PKG_NAME} ${ROS_WS}/src/${PKG_NAME}

RUN cd ${ROS_WS} \
&& apt update \
&& rosdep update \
&& rosdep install --from-paths src -y \
&& rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN source "/opt/ros/$ROS_DISTRO/setup.bash" \
&& cd $ROS_WS \
&& colcon build \
&& rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

WORKDIR ${ROS_WS}
